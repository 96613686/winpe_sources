# SmbCamSerializeToken

- ea: `0x140087730`
- end: `0x140087897`
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
- `0x140087730`

## import_xrefs

- `ntoskrnl!ExReleaseFastResource` at `0x140087855`
- `ntoskrnl!ExReleaseFastResource` at `0x140087873`
- `ntoskrnl!ExReleaseFastResource` at `0x140087855`
- `ntoskrnl!ExReleaseFastResource` at `0x140087873`
- `ntoskrnl!SeQueryInformationToken` at `0x1400877c2`
- `ntoskrnl!SeQueryInformationToken` at `0x1400877c2`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140087764`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140087764`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400877fc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400877fc`

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
0x140087730  push    rbx
0x140087732  push    rsi
0x140087733  push    rdi
0x140087734  push    r14
0x140087736  sub     rsp, 98h
0x14008773d  xor     edx, edx; Val
0x14008773f  mov     [rsp+0B8h+var_88], 0
0x140087748  mov     r14, r8
0x14008774b  mov     rbx, rcx
0x14008774e  lea     rcx, [rsp+0B8h+var_78]; void *
0x140087753  mov     rsi, r9
0x140087756  lea     r8d, [rdx+48h]; Size
0x14008775a  call    memset
0x14008775f  lea     rcx, [rsp+0B8h+var_78]
0x140087764  call    cs:__imp_ExInitializeFastOwnerEntry
0x14008776b  nop     dword ptr [rax+rax+00h]
0x140087770  test    rbx, rbx
0x140087773  jnz     short loc_14008777C
0x140087775  call    ?CreateFromCurrentToken@ClientToken@@SAPEAV1@XZ; ClientToken::CreateFromCurrentToken(void)
0x14008777a  jmp     short loc_140087784
0x14008777c  mov     rcx, rbx; struct _SECURITY_SUBJECT_CONTEXT *
0x14008777f  call    ?CreateFromSubjectContext@ClientToken@@SAPEAV1@PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; ClientToken::CreateFromSubjectContext(_SECURITY_SUBJECT_CONTEXT *)
0x140087784  mov     rdi, rax
0x140087787  test    rax, rax
0x14008778a  jnz     short loc_140087796
0x14008778c  mov     ebx, 0C0000001h
0x140087791  jmp     loc_140087887
0x140087796  cmp     dword ptr [rdi+0Ch], 2
0x14008779a  jge     short loc_1400877A6
0x14008779c  mov     ebx, 0C00000A5h
0x1400877a1  jmp     loc_14008787F
0x1400877a6  mov     rcx, [rdi]; Token
0x1400877a9  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1400877b1  mov     edx, 1Dh; TokenInformationClass
0x1400877b6  mov     [rsp+0B8h+TokenInformation], 0
0x1400877c2  call    cs:__imp_SeQueryInformationToken
0x1400877c9  nop     dword ptr [rax+rax+00h]
0x1400877ce  mov     ebx, eax
0x1400877d0  test    eax, eax
0x1400877d2  js      loc_14008787F
0x1400877d8  cmp     [rsp+0B8h+TokenInformation], 0
0x1400877e1  jz      short loc_1400877ED
0x1400877e3  mov     ebx, 0C0000022h
0x1400877e8  jmp     loc_14008787F
0x1400877ed  mov     r8b, 1
0x1400877f0  lea     rdx, [rsp+0B8h+var_78]
0x1400877f5  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x1400877fc  call    cs:__imp_ExAcquireFastResourceShared
0x140087803  nop     dword ptr [rax+rax+00h]
0x140087808  mov     rdx, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14008780f  lea     rcx, [rsp+0B8h+var_88]
0x140087814  mov     rax, rdx
0x140087817  mov     [rsp+0B8h+var_90], 1
0x14008781c  neg     rax
0x14008781f  lea     rax, ?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A; _SID_AND_ATTRIBUTES ComputerSidAndAttributes
0x140087826  sbb     r8, r8
0x140087829  xor     r9d, r9d
0x14008782c  and     r8, rax
0x14008782f  test    rdx, rdx
0x140087832  mov     [rsp+0B8h+var_98], r8
0x140087837  mov     rdx, rdi
0x14008783a  setnz   r9b
0x14008783e  call    ?CreateTicketFromUserToken@?$ClusterTicketManager@VImpKernelMode@@@@QEAAJPEAVClientToken@@KKPEAU_SID_AND_ATTRIBUTES@@_N@Z; ClusterTicketManager<ImpKernelMode>::CreateTicketFromUserToken(ClientToken *,ulong,ulong,_SID_AND_ATTRIBUTES *,bool)
0x140087843  lea     rdx, [rsp+0B8h+var_78]
0x140087848  mov     ebx, eax
0x14008784a  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x140087851  test    eax, eax
0x140087853  js      short loc_140087873
0x140087855  call    cs:__imp_ExReleaseFastResource
0x14008785c  nop     dword ptr [rax+rax+00h]
0x140087861  mov     rax, [rsp+0B8h+var_88]
0x140087866  xor     ebx, ebx
0x140087868  mov     [r14], rax
0x14008786b  movzx   ecx, word ptr [rax+2]
0x14008786f  mov     [rsi], ecx
0x140087871  jmp     short loc_14008787F
0x140087873  call    cs:__imp_ExReleaseFastResource
0x14008787a  nop     dword ptr [rax+rax+00h]
0x14008787f  mov     rcx, rdi; P
0x140087882  call    ??_GClientToken@@QEAAPEAXI@Z; ClientToken::`scalar deleting destructor'(uint)
0x140087887  mov     eax, ebx
0x140087889  add     rsp, 98h
0x140087890  pop     r14
0x140087892  pop     rdi
0x140087893  pop     rsi
0x140087894  pop     rbx
0x140087895  retn
```
