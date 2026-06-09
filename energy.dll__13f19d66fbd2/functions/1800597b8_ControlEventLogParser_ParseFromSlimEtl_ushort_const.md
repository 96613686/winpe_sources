# ControlEventLogParser::ParseFromSlimEtl(ushort const *)

- ea: `0x1800597b8`
- end: `0x1800599ea`
- name: `?ParseFromSlimEtl@ControlEventLogParser@@AEAAKPEBG@Z`
- size: `562`
- prototype: `unsigned int __fastcall(ControlEventLogParser *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18005956c`

## callees

- `0x180004e20`
- `0x180027dc8`
- `0x1800487b8`
- `0x18004ca90`
- `0x18004d8d8`
- `0x18004d8fc`
- `0x1800592d4`
- `0x180059440`
- `0x1800597b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005983f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005983f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005984e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005984e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800599b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800599b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ControlEventLogParser::ParseFromSlimEtl(ControlEventLogParser *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  ControlEventLogParser *v5; // rcx
  void *v6; // r12
  DWORD LastError; // ebx
  __int64 v8; // rcx
  ControlEventLogParser *v9; // rcx
  char *v10; // r15
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rsi
  USHORT v15; // bx
  UCHAR v16; // di
  char *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h]
  _BYTE v20[19]; // [rsp+5Dh] [rbp-A3h]
  struct _EVENT_RECORD v21; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf1; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-10h]
  __int128 Buf2; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v25; // [rsp+108h] [rbp+8h]

  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&v18);
  memset_0(&v21, 0, sizeof(v21));
  Buf1 = 0;
  v23 = 0;
  Buf2 = 0;
  v25 = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    LastError = ControlEventLogParser::LoadSlimEtlHeader(v5, FileW, (struct _SLEEPSTUDY_CONTROL_ETL_HEADER *)&Buf1);
    if ( !LastError )
    {
      while ( 1 )
      {
        LastError = ControlEventLogParser::LoadSlimEtlEvents(v8, v6, &Buf1, (LPVOID *)&v18);
        if ( LastError )
          break;
        LastError = ControlEventLogParser::LoadSlimEtlHeader(v9, v6, (struct _SLEEPSTUDY_CONTROL_ETL_HEADER *)&Buf2);
        if ( LastError )
          break;
        if ( !memcmp_0(&Buf1, &Buf2, 0x18u) )
        {
          v10 = v18;
          v11 = v19 - (_QWORD)v18;
          if ( (unsigned __int64)(v19 - (_QWORD)v18) >= 2 )
          {
            do
            {
              v12 = *(unsigned __int16 *)&v18[v11 - 2];
              if ( (unsigned int)v12 < 0x22 )
                break;
              if ( v11 < v12 )
                break;
              v13 = *(unsigned __int16 *)&v18[v11 - v12] + 26;
              if ( v13 != (_DWORD)v12 )
                break;
              v11 -= v13;
            }
            while ( v11 >= 2 );
            for ( ; v11 < v19 - (__int64)v18; v10 = v18 )
            {
              v14 = *(unsigned __int16 *)&v10[v11];
              v15 = *(_WORD *)&v10[v11 + 2];
              v16 = v10[v11 + 4];
              *(_OWORD *)v20 = *(_OWORD *)&v10[v11 + 5];
              *(_DWORD *)&v20[15] = *(_DWORD *)&v10[v11 + 20];
              memset_0(&v21, 0, sizeof(v21));
              v21.EventHeader.EventDescriptor.Id = v15;
              v21.EventHeader.Flags = 64;
              v21.EventHeader.EventDescriptor.Version = v16;
              v21.EventHeader.ProviderId = *(GUID *)&v20[3];
              v21.UserData = &v10[v11 + 24];
              v21.UserDataLength = v14;
              v21.UserContext = this;
              ControlEventLogParser::DispatchEvent(this, &v21);
              v11 += v14 + 26;
            }
          }
          LastError = 0;
          break;
        }
        Buf1 = Buf2;
        v23 = v25;
      }
    }
    CloseHandle(v6);
  }
  std::vector<unsigned char>::_Tidy(&v18);
  return LastError;
}

```

## disassembly

```asm
0x1800597b8  mov     [rsp-8+arg_10], rbx
0x1800597bd  push    rbp
0x1800597be  push    rsi
0x1800597bf  push    rdi
0x1800597c0  push    r12
0x1800597c2  push    r13
0x1800597c4  push    r14
0x1800597c6  push    r15
0x1800597c8  lea     rbp, [rsp-20h]
0x1800597cd  sub     rsp, 120h
0x1800597d4  mov     rax, cs:__security_cookie
0x1800597db  xor     rax, rsp
0x1800597de  mov     [rbp+50h+var_40], rax
0x1800597e2  mov     rbx, rdx
0x1800597e5  mov     r13, rcx
0x1800597e8  lea     rcx, [rsp+150h+var_110]; void *
0x1800597ed  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x1800597f2  nop
0x1800597f3  xor     edx, edx; Val
0x1800597f5  lea     r8d, [rdx+70h]; Size
0x1800597f9  lea     rcx, [rsp+150h+var_E0]; void *
0x1800597fe  call    memset_0
0x180059803  xorps   xmm0, xmm0
0x180059806  xor     eax, eax
0x180059808  movups  [rbp+50h+Buf1], xmm0
0x18005980c  mov     [rbp+50h+var_60], rax
0x180059810  xorps   xmm1, xmm1
0x180059813  movups  [rbp+50h+Buf2], xmm1
0x180059817  mov     [rbp+50h+var_48], rax
0x18005981b  mov     [rsp+150h+hTemplateFile], rax; hTemplateFile
0x180059820  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180059828  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x180059830  xor     r9d, r9d; lpSecurityAttributes
0x180059833  mov     edx, 80000000h; dwDesiredAccess
0x180059838  lea     r8d, [rax+7]; dwShareMode
0x18005983c  mov     rcx, rbx; lpFileName
0x18005983f  call    cs:__imp_CreateFileW
0x180059845  mov     r12, rax
0x180059848  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005984c  jnz     short loc_18005985B
0x18005984e  call    cs:__imp_GetLastError
0x180059854  mov     ebx, eax
0x180059856  jmp     loc_1800599B7
0x18005985b  lea     r8, [rbp+50h+Buf1]; struct _SLEEPSTUDY_CONTROL_ETL_HEADER *
0x18005985f  mov     rdx, r12; void *
0x180059862  call    ?LoadSlimEtlHeader@ControlEventLogParser@@AEAAKPEAXPEAU_SLEEPSTUDY_CONTROL_ETL_HEADER@@@Z; ControlEventLogParser::LoadSlimEtlHeader(void *,_SLEEPSTUDY_CONTROL_ETL_HEADER *)
0x180059867  mov     ebx, eax
0x180059869  test    eax, eax
0x18005986b  jnz     loc_1800599AD
0x180059871  lea     r9, [rsp+150h+var_110]
0x180059876  lea     r8, [rbp+50h+Buf1]
0x18005987a  mov     rdx, r12
0x18005987d  call    ?LoadSlimEtlEvents@ControlEventLogParser@@AEAAKPEAXPEAU_SLEEPSTUDY_CONTROL_ETL_HEADER@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; ControlEventLogParser::LoadSlimEtlEvents(void *,_SLEEPSTUDY_CONTROL_ETL_HEADER *,std::vector<uchar> &)
0x180059882  mov     ebx, eax
0x180059884  test    eax, eax
0x180059886  jnz     loc_1800599AD
0x18005988c  lea     r8, [rbp+50h+Buf2]; struct _SLEEPSTUDY_CONTROL_ETL_HEADER *
0x180059890  mov     rdx, r12; void *
0x180059893  call    ?LoadSlimEtlHeader@ControlEventLogParser@@AEAAKPEAXPEAU_SLEEPSTUDY_CONTROL_ETL_HEADER@@@Z; ControlEventLogParser::LoadSlimEtlHeader(void *,_SLEEPSTUDY_CONTROL_ETL_HEADER *)
0x180059898  mov     ebx, eax
0x18005989a  test    eax, eax
0x18005989c  jnz     loc_1800599AD
0x1800598a2  lea     r8d, [rax+18h]; Size
0x1800598a6  lea     rdx, [rbp+50h+Buf2]; Buf2
0x1800598aa  lea     rcx, [rbp+50h+Buf1]; Buf1
0x1800598ae  call    memcmp_0
0x1800598b3  test    eax, eax
0x1800598b5  jz      short loc_1800598CB
0x1800598b7  movups  xmm0, [rbp+50h+Buf2]
0x1800598bb  movups  [rbp+50h+Buf1], xmm0
0x1800598bf  movsd   xmm1, [rbp+50h+var_48]
0x1800598c4  movsd   [rbp+50h+var_60], xmm1
0x1800598c9  jmp     short loc_180059871
0x1800598cb  mov     rcx, [rsp+150h+var_108]
0x1800598d0  mov     r15, [rsp+150h+var_110]
0x1800598d5  sub     rcx, r15
0x1800598d8  mov     r14, rcx
0x1800598db  cmp     rcx, 2
0x1800598df  jb      loc_1800599AB
0x1800598e5  movzx   edx, word ptr [r15+r14-2]
0x1800598eb  cmp     edx, 22h ; '"'
0x1800598ee  jb      short loc_180059915
0x1800598f0  cmp     r14, rdx
0x1800598f3  jb      short loc_180059915
0x1800598f5  mov     rax, r15
0x1800598f8  sub     rax, rdx
0x1800598fb  movzx   r8d, word ptr [rax+r14]
0x180059900  add     r8d, 1Ah
0x180059904  cmp     r8d, edx
0x180059907  jnz     short loc_180059915
0x180059909  mov     eax, r8d
0x18005990c  sub     r14, rax
0x18005990f  cmp     r14, 2
0x180059913  jnb     short loc_1800598E5
0x180059915  cmp     r14, rcx
0x180059918  jnb     loc_1800599AB
0x18005991e  movzx   esi, word ptr [r15+r14]
0x180059923  movzx   ebx, word ptr [r15+r14+2]
0x180059929  mov     dil, [r15+r14+4]
0x18005992e  movups  xmm0, xmmword ptr [r15+r14+5]
0x180059934  movups  xmmword ptr [rsp+150h+var_F3], xmm0
0x180059939  mov     eax, [r15+r14+14h]
0x18005993e  mov     dword ptr [rsp+150h+var_F3+0Fh], eax
0x180059942  xor     edx, edx; Val
0x180059944  lea     r8d, [rdx+70h]; Size
0x180059948  lea     rcx, [rsp+150h+var_E0]; void *
0x18005994d  call    memset_0
0x180059952  mov     [rbp+50h+var_E0.EventHeader.EventDescriptor.Id], bx
0x180059956  mov     eax, 40h ; '@'
0x18005995b  mov     [rsp+150h+var_E0.EventHeader.Flags], ax
0x180059960  mov     [rbp+50h+var_E0.EventHeader.EventDescriptor.Version], dil
0x180059964  movups  xmm0, xmmword ptr [rsp+150h+var_F3+3]
0x180059969  movdqu  xmmword ptr [rbp+50h+var_E0.EventHeader.ProviderId.Data1], xmm0
0x18005996e  lea     rax, [r15+18h]
0x180059972  add     rax, r14
0x180059975  mov     [rbp+50h+var_E0.UserData], rax
0x180059979  mov     [rbp+50h+var_E0.UserDataLength], si
0x18005997d  mov     [rbp+50h+var_E0.UserContext], r13
0x180059981  lea     rdx, [rsp+150h+var_E0]; struct _EVENT_RECORD *
0x180059986  mov     rcx, r13; this
0x180059989  call    ?DispatchEvent@ControlEventLogParser@@AEAAXPEAU_EVENT_RECORD@@@Z; ControlEventLogParser::DispatchEvent(_EVENT_RECORD *)
0x18005998e  lea     rax, [rsi+1Ah]
0x180059992  add     r14, rax
0x180059995  mov     rax, [rsp+150h+var_108]
0x18005999a  mov     r15, [rsp+150h+var_110]
0x18005999f  sub     rax, r15
0x1800599a2  cmp     r14, rax
0x1800599a5  jb      loc_18005991E
0x1800599ab  xor     ebx, ebx
0x1800599ad  mov     rcx, r12; hObject
0x1800599b0  call    cs:__imp_CloseHandle
0x1800599b6  nop
0x1800599b7  lea     rcx, [rsp+150h+var_110]
0x1800599bc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800599c1  mov     eax, ebx
0x1800599c3  mov     rcx, [rbp+50h+var_40]
0x1800599c7  xor     rcx, rsp; StackCookie
0x1800599ca  call    __security_check_cookie
0x1800599cf  mov     rbx, [rsp+150h+arg_10]
0x1800599d7  add     rsp, 120h
0x1800599de  pop     r15
0x1800599e0  pop     r14
0x1800599e2  pop     r13
0x1800599e4  pop     r12
0x1800599e6  pop     rdi
0x1800599e7  pop     rsi
0x1800599e8  pop     rbp
0x1800599e9  retn
```
