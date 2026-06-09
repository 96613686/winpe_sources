# SmbCamSerializeToken

- ea: `0x1400876e0`
- end: `0x140087847`
- name: `SmbCamSerializeToken`
- size: `359`
- prototype: `__int64 __fastcall(struct _SECURITY_SUBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400302f0`

## callees

- `0x14004e234`
- `0x14004e544`
- `0x14004e638`
- `0x14004e6ec`
- `0x14005a200`
- `0x1400876e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastResource` at `0x140087805`
- `ntoskrnl!ExReleaseFastResource` at `0x140087823`
- `ntoskrnl!ExReleaseFastResource` at `0x140087805`
- `ntoskrnl!ExReleaseFastResource` at `0x140087823`
- `ntoskrnl!SeQueryInformationToken` at `0x140087772`
- `ntoskrnl!SeQueryInformationToken` at `0x140087772`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140087714`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140087714`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400877ac`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400877ac`

## pseudocode

```c
__int64 __fastcall SmbCamSerializeToken(
        struct _SECURITY_SUBJECT_CONTEXT *a1,
        __int64 a2,
        unsigned __int16 **a3,
        _DWORD *a4)
{
  struct ClientToken *v7; // rax
  unsigned int v8; // edx
  struct ClientToken *v9; // rdi
  int TicketFromUserToken; // ebx
  void *v11; // rcx
  __int64 v12; // r8
  unsigned __int16 *v13; // rax
  unsigned __int16 *v15; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v16[120]; // [rsp+40h] [rbp-78h] BYREF
  PVOID TokenInformation; // [rsp+C0h] [rbp+8h] BYREF

  v15 = 0;
  memset(v16, 0, 0x48u);
  ExInitializeFastOwnerEntry(v16);
  if ( a1 )
    v7 = ClientToken::CreateFromSubjectContext(a1);
  else
    v7 = ClientToken::CreateFromCurrentToken();
  v9 = v7;
  if ( v7 )
  {
    if ( *((int *)v7 + 3) >= 2 )
    {
      v11 = *(void **)v7;
      TokenInformation = 0;
      TicketFromUserToken = SeQueryInformationToken(v11, TokenIsAppContainer, &TokenInformation);
      if ( TicketFromUserToken >= 0 )
      {
        if ( TokenInformation )
        {
          TicketFromUserToken = -1073741790;
        }
        else
        {
          LOBYTE(v12) = 1;
          ExAcquireFastResourceShared(&GlobalResource, v16, v12);
          TicketFromUserToken = ClusterTicketManager<ImpKernelMode>::CreateTicketFromUserToken(
                                  (PVOID *)&v15,
                                  (__int64)v9,
                                  (unsigned __int64)&ComputerSidAndAttributes
                                & -(__int64)(*(_QWORD *)&ComputerSidAndAttributes.Revision != 0),
                                  *(_QWORD *)&ComputerSidAndAttributes.Revision != 0,
                                  (unsigned __int64)&ComputerSidAndAttributes
                                & -(__int64)(*(_QWORD *)&ComputerSidAndAttributes.Revision != 0),
                                  1);
          ExReleaseFastResource(&GlobalResource, v16);
          if ( TicketFromUserToken >= 0 )
          {
            v13 = v15;
            TicketFromUserToken = 0;
            *a3 = v15;
            *a4 = v13[1];
          }
        }
      }
    }
    else
    {
      TicketFromUserToken = -1073741659;
    }
    ClientToken::`scalar deleting destructor'(v9, v8);
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)TicketFromUserToken;
}

```

## disassembly

```asm
0x1400876e0  push    rbx
0x1400876e2  push    rsi
0x1400876e3  push    rdi
0x1400876e4  push    r14
0x1400876e6  sub     rsp, 98h
0x1400876ed  xor     edx, edx; Val
0x1400876ef  mov     [rsp+0B8h+var_88], 0
0x1400876f8  mov     r14, r8
0x1400876fb  mov     rbx, rcx
0x1400876fe  lea     rcx, [rsp+0B8h+var_78]; void *
0x140087703  mov     rsi, r9
0x140087706  lea     r8d, [rdx+48h]; Size
0x14008770a  call    memset
0x14008770f  lea     rcx, [rsp+0B8h+var_78]
0x140087714  call    cs:__imp_ExInitializeFastOwnerEntry
0x14008771b  nop     dword ptr [rax+rax+00h]
0x140087720  test    rbx, rbx
0x140087723  jnz     short loc_14008772C
0x140087725  call    ?CreateFromCurrentToken@ClientToken@@SAPEAV1@XZ; ClientToken::CreateFromCurrentToken(void)
0x14008772a  jmp     short loc_140087734
0x14008772c  mov     rcx, rbx; struct _SECURITY_SUBJECT_CONTEXT *
0x14008772f  call    ?CreateFromSubjectContext@ClientToken@@SAPEAV1@PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; ClientToken::CreateFromSubjectContext(_SECURITY_SUBJECT_CONTEXT *)
0x140087734  mov     rdi, rax
0x140087737  test    rax, rax
0x14008773a  jnz     short loc_140087746
0x14008773c  mov     ebx, 0C0000001h
0x140087741  jmp     loc_140087837
0x140087746  cmp     dword ptr [rdi+0Ch], 2
0x14008774a  jge     short loc_140087756
0x14008774c  mov     ebx, 0C00000A5h
0x140087751  jmp     loc_14008782F
0x140087756  mov     rcx, [rdi]; Token
0x140087759  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x140087761  mov     edx, 1Dh; TokenInformationClass
0x140087766  mov     [rsp+0B8h+TokenInformation], 0
0x140087772  call    cs:__imp_SeQueryInformationToken
0x140087779  nop     dword ptr [rax+rax+00h]
0x14008777e  mov     ebx, eax
0x140087780  test    eax, eax
0x140087782  js      loc_14008782F
0x140087788  cmp     [rsp+0B8h+TokenInformation], 0
0x140087791  jz      short loc_14008779D
0x140087793  mov     ebx, 0C0000022h
0x140087798  jmp     loc_14008782F
0x14008779d  mov     r8b, 1
0x1400877a0  lea     rdx, [rsp+0B8h+var_78]
0x1400877a5  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x1400877ac  call    cs:__imp_ExAcquireFastResourceShared
0x1400877b3  nop     dword ptr [rax+rax+00h]
0x1400877b8  mov     rdx, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x1400877bf  lea     rcx, [rsp+0B8h+var_88]
0x1400877c4  mov     rax, rdx
0x1400877c7  mov     [rsp+0B8h+var_90], 1
0x1400877cc  neg     rax
0x1400877cf  lea     rax, ?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A; _SID_AND_ATTRIBUTES ComputerSidAndAttributes
0x1400877d6  sbb     r8, r8
0x1400877d9  xor     r9d, r9d
0x1400877dc  and     r8, rax
0x1400877df  test    rdx, rdx
0x1400877e2  mov     [rsp+0B8h+var_98], r8
0x1400877e7  mov     rdx, rdi
0x1400877ea  setnz   r9b
0x1400877ee  call    ?CreateTicketFromUserToken@?$ClusterTicketManager@VImpKernelMode@@@@QEAAJPEAVClientToken@@KKPEAU_SID_AND_ATTRIBUTES@@_N@Z; ClusterTicketManager<ImpKernelMode>::CreateTicketFromUserToken(ClientToken *,ulong,ulong,_SID_AND_ATTRIBUTES *,bool)
0x1400877f3  lea     rdx, [rsp+0B8h+var_78]
0x1400877f8  mov     ebx, eax
0x1400877fa  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x140087801  test    eax, eax
0x140087803  js      short loc_140087823
0x140087805  call    cs:__imp_ExReleaseFastResource
0x14008780c  nop     dword ptr [rax+rax+00h]
0x140087811  mov     rax, [rsp+0B8h+var_88]
0x140087816  xor     ebx, ebx
0x140087818  mov     [r14], rax
0x14008781b  movzx   ecx, word ptr [rax+2]
0x14008781f  mov     [rsi], ecx
0x140087821  jmp     short loc_14008782F
0x140087823  call    cs:__imp_ExReleaseFastResource
0x14008782a  nop     dword ptr [rax+rax+00h]
0x14008782f  mov     rcx, rdi; P
0x140087832  call    ??_GClientToken@@QEAAPEAXI@Z; ClientToken::`scalar deleting destructor'(uint)
0x140087837  mov     eax, ebx
0x140087839  add     rsp, 98h
0x140087840  pop     r14
0x140087842  pop     rdi
0x140087843  pop     rsi
0x140087844  pop     rbx
0x140087845  retn
```
