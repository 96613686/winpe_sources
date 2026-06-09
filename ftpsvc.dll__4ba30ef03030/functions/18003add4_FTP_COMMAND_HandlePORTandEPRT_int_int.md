# FTP_COMMAND::HandlePORTandEPRT(int *,int)

- ea: `0x18003add4`
- end: `0x18003b124`
- name: `?HandlePORTandEPRT@FTP_COMMAND@@AEAAXPEAHH@Z`
- size: `848`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x18002c580`
- `0x18002c7a8`
- `0x180038ac0`
- `0x18003add4`
- `0x18003e564`
- `0x18003e980`
- `0x18003f6b0`
- `0x18003f9b4`
- `0x18003fed0`
- `0x18003ff84`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18003b000`
- `WS2_32!__imp_ntohs` at `0x18003b000`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b0f6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b0f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b042`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b042`
- `iisutil!WriteRefTraceLog` at `0x18003b0d4`
- `iisutil!WriteRefTraceLog` at `0x18003b0d4`

## string_xrefs

- `0x18003b07d`: `%s command successful.`
- `0x18003ae54`: `Command not understood. Use EPSV command.`
- `0x18003af72`: `Mismatched network protocol between control and data connection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_COMMAND::HandlePORTandEPRT(FTP_COMMAND *this, int *a2, int a3)
{
  _QWORD *v6; // r14
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rdi
  int v8; // ecx
  int v9; // ecx
  const char *v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  __int16 v18; // r8
  bool v19; // zf
  int active; // eax
  unsigned __int32 v21; // ebx
  int v22[4]; // [rsp+30h] [rbp-79h] BYREF
  struct sockaddr_storage v23; // [rsp+40h] [rbp-69h] BYREF

  v6 = (_QWORD *)*((_QWORD *)this + 132);
  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig((FTP_SESSION *)v6);
  memset_0(&v23, 0, sizeof(v23));
  v22[0] = 0;
  *a2 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 132) + 4812LL) )
  {
    if ( !*((_DWORD *)this + 292) )
      *((_DWORD *)this + 292) = -2147024874;
    FTP_COMMAND::WriteResponseAndLog(this, "550", "Command not understood. Use EPSV command.");
    goto LABEL_49;
  }
  v8 = *((_DWORD *)this + 234);
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 7 )
      {
LABEL_49:
        *a2 = 1;
        goto LABEL_50;
      }
LABEL_8:
      v10 = (const char *)*((_QWORD *)this + 20);
      if ( a3 )
        v11 = ParseEPRTCmdStringIntoAddress(v10, &v23);
      else
        v11 = ParsePORTCmdStringIntoAddress(v10, &v23);
      if ( v11 < 0 )
      {
        if ( !*((_DWORD *)this + 292) )
          *((_DWORD *)this + 292) = v11;
LABEL_43:
        FTP_COMMAND::WriteResponseAndLog(this, "501", "Server cannot accept argument.");
        goto LABEL_49;
      }
      v16 = v6[135];
      if ( *(_DWORD *)(v16 + 12) != v23.ss_family )
      {
        if ( !*((_DWORD *)this + 292) )
          *((_DWORD *)this + 292) = -2147024809;
        FTP_COMMAND::WriteResponseAndLog(this, "522", "Mismatched network protocol between control and data connection");
        goto LABEL_49;
      }
      if ( v23.ss_family == 23 && *(_WORD *)(v16 + 448) == 23 )
      {
        v17 = *(_DWORD *)(v16 + 472);
        *(_DWORD *)&v23.__ss_pad2[8] = v17;
      }
      else
      {
        v17 = *(_DWORD *)&v23.__ss_pad2[8];
      }
      if ( *((_DWORD *)ReferencedSiteConfig + 176) )
      {
        v18 = *(_WORD *)(v16 + 448);
        if ( v23.ss_family == 23 )
        {
          if ( v18 != 23 || v17 != *(_DWORD *)(v16 + 472) || *(_QWORD *)v23.__ss_pad2 != *(_QWORD *)(v16 + 464) )
            goto LABEL_39;
          v19 = v23.__ss_align == *(_QWORD *)(v16 + 456);
        }
        else
        {
          if ( v18 != 2 )
          {
LABEL_39:
            if ( !*((_DWORD *)this + 292) )
              *((_DWORD *)this + 292) = -2147024809;
            if ( !*((_DWORD *)this + 274) )
            {
              *((_DWORD *)this + 274) = 38;
              STRU::Copy(
                (FTP_COMMAND *)((char *)this + 1112),
                L"Client IP on the control channel didn't match the client IP on the data channel.");
              *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
            }
            goto LABEL_43;
          }
          v19 = *(_DWORD *)&v23.__ss_pad1[2] == *(_DWORD *)(v16 + 452);
        }
        if ( !v19 || ntohs(*(u_short *)v23.__ss_pad1) < 0x400u )
          goto LABEL_39;
      }
      active = FTP_DATA_CHANNEL::EstablishActiveConnectionOnBackground(
                 (FTP_DATA_CHANNEL *)(v6 + 259),
                 (const struct sockaddr *)&v23);
      if ( active < 0 )
      {
        if ( !*((_DWORD *)this + 292) )
          *((_DWORD *)this + 292) = active;
        FTP_COMMAND::WriteResponseWithErrorTextAndLog(this, "550");
      }
      else
      {
        FTP_COMMAND::WriteResponseAndLog(this, "200", "%s command successful.", *((const char **)this + 6));
      }
      goto LABEL_49;
    }
  }
  else
  {
    FTP_DATA_CHANNEL::InitiateChannelShutdown((FTP_DATA_CHANNEL *)(v6 + 259), -2147023673, 0, &WideCharStr, 0);
    *((_DWORD *)this + 234) = 1;
    v12 = FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(
            (FTP_DATA_CHANNEL *)(v6 + 259),
            (FTP_COMMAND *)((char *)this + 872),
            v22);
    v13 = v22[0];
    if ( v12 < 0 )
      v13 = 0;
    v22[0] = v13;
    if ( v13 )
      goto LABEL_50;
  }
  *((_DWORD *)this + 234) = 8;
  v14 = FTP_DATA_CHANNEL::NotifyOnShutdownCompletion(
          (FTP_DATA_CHANNEL *)(v6 + 259),
          (FTP_COMMAND *)((char *)this + 872),
          v22);
  v15 = v22[0];
  if ( v14 < 0 )
    v15 = 0;
  if ( !v15 )
    goto LABEL_8;
LABEL_50:
  v21 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v21);
  if ( !v21 )
  {
    if ( ReferencedSiteConfig )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
    }
  }
}

```

## disassembly

```asm
0x18003add4  mov     [rsp-8+arg_10], rbx
0x18003add9  push    rbp
0x18003adda  push    rsi
0x18003addb  push    rdi
0x18003addc  push    r12
0x18003adde  push    r13
0x18003ade0  push    r14
0x18003ade2  push    r15
0x18003ade4  lea     rbp, [rsp-27h]
0x18003ade9  sub     rsp, 0D0h
0x18003adf0  mov     rax, cs:__security_cookie
0x18003adf7  xor     rax, rsp
0x18003adfa  mov     [rbp+57h+var_40], rax
0x18003adfe  mov     r12d, r8d
0x18003ae01  mov     r13, rdx
0x18003ae04  mov     rbx, rcx
0x18003ae07  mov     r14, [rcx+420h]
0x18003ae0e  mov     rcx, r14; this
0x18003ae11  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003ae16  mov     rdi, rax
0x18003ae19  xor     edx, edx; Val
0x18003ae1b  mov     r8d, 80h; Size
0x18003ae21  lea     rcx, [rbp+57h+var_C0]; void *
0x18003ae25  call    memset_0
0x18003ae2a  xor     esi, esi
0x18003ae2c  mov     [rbp+57h+var_D0], esi
0x18003ae2f  mov     [r13+0], esi
0x18003ae33  mov     rdx, [rbx+420h]
0x18003ae3a  cmp     [rdx+12CCh], esi
0x18003ae40  jz      short loc_18003AE6F
0x18003ae42  cmp     [rbx+490h], esi
0x18003ae48  jnz     short loc_18003AE54
0x18003ae4a  mov     dword ptr [rbx+490h], 80070016h
0x18003ae54  lea     r8, aCommandNotUnde_0; "Command not understood. Use EPSV comman"...
0x18003ae5b  lea     rdx, a550; "550"
0x18003ae62  mov     rcx, rbx; this
0x18003ae65  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003ae6a  jmp     loc_18003B0B2
0x18003ae6f  lea     r15, [r14+818h]
0x18003ae76  lea     rsi, [rbx+368h]
0x18003ae7d  mov     ecx, [rbx+3A8h]
0x18003ae83  test    ecx, ecx
0x18003ae85  jz      short loc_18003AEB5
0x18003ae87  sub     ecx, 1
0x18003ae8a  jz      short loc_18003AF03
0x18003ae8c  cmp     ecx, 7
0x18003ae8f  jnz     loc_18003B0B2
0x18003ae95  xor     esi, esi
0x18003ae97  mov     rcx, [rbx+0A0h]; char *
0x18003ae9e  lea     rdx, [rbp+57h+var_C0]; struct sockaddr_storage *
0x18003aea2  test    r12d, r12d
0x18003aea5  jz      loc_18003AF30
0x18003aeab  call    ?ParseEPRTCmdStringIntoAddress@@YAJPEBDPEAUsockaddr_storage@@@Z; ParseEPRTCmdStringIntoAddress(char const *,sockaddr_storage *)
0x18003aeb0  jmp     loc_18003AF35
0x18003aeb5  mov     [rsp+100h+var_E0], 0; int
0x18003aebd  lea     r9, WideCharStr; unsigned __int16 *
0x18003aec4  xor     r8d, r8d; unsigned int
0x18003aec7  mov     edx, 800704C7h; int
0x18003aecc  mov     rcx, r15; this
0x18003aecf  call    ?InitiateChannelShutdown@FTP_DATA_CHANNEL@@QEAAXJKPEBGH@Z; FTP_DATA_CHANNEL::InitiateChannelShutdown(long,ulong,ushort const *,int)
0x18003aed4  mov     dword ptr [rsi+40h], 1
0x18003aedb  lea     r8, [rbp+57h+var_D0]; int *
0x18003aedf  mov     rdx, rsi; struct FTP_ASYNC_CONTEXT *
0x18003aee2  mov     rcx, r15; this
0x18003aee5  call    ?NotifyOnNewConnectionReady@FTP_DATA_CHANNEL@@QEAAJPEAVFTP_ASYNC_CONTEXT@@PEAH@Z; FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(FTP_ASYNC_CONTEXT *,int *)
0x18003aeea  mov     r8d, [rbp+57h+var_D0]
0x18003aeee  xor     ecx, ecx
0x18003aef0  test    eax, eax
0x18003aef2  cmovs   r8d, ecx
0x18003aef6  mov     [rbp+57h+var_D0], r8d
0x18003aefa  test    r8d, r8d
0x18003aefd  jnz     loc_18003B0BA
0x18003af03  mov     dword ptr [rsi+40h], 8
0x18003af0a  lea     r8, [rbp+57h+var_D0]; int *
0x18003af0e  mov     rdx, rsi; struct FTP_ASYNC_CONTEXT *
0x18003af11  mov     rcx, r15; this
0x18003af14  call    ?NotifyOnShutdownCompletion@FTP_DATA_CHANNEL@@QEAAJPEAVFTP_ASYNC_CONTEXT@@PEAH@Z; FTP_DATA_CHANNEL::NotifyOnShutdownCompletion(FTP_ASYNC_CONTEXT *,int *)
0x18003af19  mov     edx, [rbp+57h+var_D0]
0x18003af1c  xor     esi, esi
0x18003af1e  test    eax, eax
0x18003af20  cmovs   edx, esi
0x18003af23  test    edx, edx
0x18003af25  jnz     loc_18003B0BA
0x18003af2b  jmp     loc_18003AE97
0x18003af30  call    ?ParsePORTCmdStringIntoAddress@@YAJPEBDPEAUsockaddr_storage@@@Z; ParsePORTCmdStringIntoAddress(char const *,sockaddr_storage *)
0x18003af35  test    eax, eax
0x18003af37  jns     short loc_18003AF50
0x18003af39  cmp     [rbx+490h], esi
0x18003af3f  jnz     loc_18003B056
0x18003af45  mov     [rbx+490h], eax
0x18003af4b  jmp     loc_18003B056
0x18003af50  mov     rcx, [r14+438h]
0x18003af57  movzx   edx, [rbp+57h+var_C0.ss_family]
0x18003af5b  cmp     [rcx+0Ch], edx
0x18003af5e  jz      short loc_18003AF85
0x18003af60  cmp     [rbx+490h], esi
0x18003af66  jnz     short loc_18003AF72
0x18003af68  mov     dword ptr [rbx+490h], 80070057h
0x18003af72  lea     r8, aMismatchedNetw; "Mismatched network protocol between con"...
0x18003af79  lea     rdx, a522; "522"
0x18003af80  jmp     loc_18003AE62
0x18003af85  mov     r9w, 17h
0x18003af8a  cmp     dx, r9w
0x18003af8e  jnz     short loc_18003AFA5
0x18003af90  cmp     [rcx+1C0h], r9w
0x18003af98  jnz     short loc_18003AFA5
0x18003af9a  mov     eax, [rcx+1D8h]
0x18003afa0  mov     dword ptr [rbp+57h+var_C0.__ss_pad2+8], eax
0x18003afa3  jmp     short loc_18003AFA8
0x18003afa5  mov     eax, dword ptr [rbp+57h+var_C0.__ss_pad2+8]
0x18003afa8  cmp     [rdi+2C0h], esi
0x18003afae  jz      loc_18003B069
0x18003afb4  movzx   r8d, word ptr [rcx+1C0h]
0x18003afbc  cmp     dx, r9w
0x18003afc0  jnz     short loc_18003AFEA
0x18003afc2  cmp     r8w, r9w
0x18003afc6  jnz     short loc_18003B010
0x18003afc8  cmp     eax, [rcx+1D8h]
0x18003afce  jnz     short loc_18003B010
0x18003afd0  mov     rax, [rcx+1D0h]
0x18003afd7  cmp     qword ptr [rbp+57h+var_C0.__ss_pad2], rax
0x18003afdb  jnz     short loc_18003B010
0x18003afdd  mov     rax, [rcx+1C8h]
0x18003afe4  cmp     [rbp+57h+var_C0.__ss_align], rax
0x18003afe8  jmp     short loc_18003AFFA
0x18003afea  cmp     r8w, 2
0x18003afef  jnz     short loc_18003B010
0x18003aff1  mov     eax, [rcx+1C4h]
0x18003aff7  cmp     dword ptr [rbp+57h+var_C0.__ss_pad1+2], eax
0x18003affa  jnz     short loc_18003B010
0x18003affc  movzx   ecx, word ptr [rbp+57h+var_C0.__ss_pad1]; netshort
0x18003b000  call    cs:__imp_ntohs
0x18003b006  mov     ecx, 400h
0x18003b00b  cmp     ax, cx
0x18003b00e  jnb     short loc_18003B069
0x18003b010  cmp     [rbx+490h], esi
0x18003b016  jnz     short loc_18003B022
0x18003b018  mov     dword ptr [rbx+490h], 80070057h
0x18003b022  cmp     [rbx+448h], esi
0x18003b028  jnz     short loc_18003B056
0x18003b02a  mov     dword ptr [rbx+448h], 26h ; '&'
0x18003b034  lea     rcx, [rbx+458h]
0x18003b03b  lea     rdx, aClientIpOnTheC; "Client IP on the control channel didn't"...
0x18003b042  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003b048  mov     rax, [rbx+478h]
0x18003b04f  mov     [rbx+450h], rax
0x18003b056  lea     r8, aServerCannotAc; "Server cannot accept argument."
0x18003b05d  lea     rdx, a501; "501"
0x18003b064  jmp     loc_18003AE62
0x18003b069  lea     rdx, [rbp+57h+var_C0]; struct sockaddr *
0x18003b06d  mov     rcx, r15; this
0x18003b070  call    ?EstablishActiveConnectionOnBackground@FTP_DATA_CHANNEL@@QEAAJPEBUsockaddr@@@Z; FTP_DATA_CHANNEL::EstablishActiveConnectionOnBackground(sockaddr const *)
0x18003b075  test    eax, eax
0x18003b077  js      short loc_18003B095
0x18003b079  mov     r9, [rbx+30h]
0x18003b07d  lea     r8, aSCommandSucces; "%s command successful."
0x18003b084  lea     rdx, a200; "200"
0x18003b08b  mov     rcx, rbx; this
0x18003b08e  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b093  jmp     short loc_18003B0B2
0x18003b095  cmp     [rbx+490h], esi
0x18003b09b  jnz     short loc_18003B0A3
0x18003b09d  mov     [rbx+490h], eax
0x18003b0a3  lea     rdx, a550; "550"
0x18003b0aa  mov     rcx, rbx; this
0x18003b0ad  call    ?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)
0x18003b0b2  mov     dword ptr [r13+0], 1
0x18003b0ba  or      ebx, 0FFFFFFFFh
0x18003b0bd  lock xadd [rdi], ebx
0x18003b0c1  dec     ebx
0x18003b0c3  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003b0ca  test    rcx, rcx
0x18003b0cd  jz      short loc_18003B0DA
0x18003b0cf  mov     r8, rdi
0x18003b0d2  mov     edx, ebx
0x18003b0d4  call    cs:__imp_WriteRefTraceLog
0x18003b0da  test    ebx, ebx
0x18003b0dc  jnz     short loc_18003B0FD
0x18003b0de  test    rdi, rdi
0x18003b0e1  jz      short loc_18003B0FD
0x18003b0e3  mov     rcx, rdi; this
0x18003b0e6  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003b0eb  nop
0x18003b0ec  mov     rdx, rdi
0x18003b0ef  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003b0f6  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003b0fc  nop
0x18003b0fd  mov     rcx, [rbp+57h+var_40]
0x18003b101  xor     rcx, rsp; StackCookie
0x18003b104  call    __security_check_cookie
0x18003b109  mov     rbx, [rsp+100h+arg_10]
0x18003b111  add     rsp, 0D0h
0x18003b118  pop     r15
0x18003b11a  pop     r14
0x18003b11c  pop     r13
0x18003b11e  pop     r12
0x18003b120  pop     rdi
0x18003b121  pop     rsi
0x18003b122  pop     rbp
0x18003b123  retn
```
