# InitDesktopWinsta(void)

- ea: `0x180002e34`
- end: `0x18000310f`
- name: `?InitDesktopWinsta@@YAJXZ`
- size: `731`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x1800028f8`
- `0x180002e34`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002ee6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002fe9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002ee6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002fe9`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002ecb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002fb2`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002ecb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002fb2`
- `KERNEL32!GetLastError` at `0x180002fbc`
- `KERNEL32!GetLastError` at `0x180003041`
- `KERNEL32!GetLastError` at `0x180002fbc`
- `KERNEL32!GetLastError` at `0x180003041`
- `KERNEL32!GetCurrentThreadId` at `0x180002f06`
- `KERNEL32!GetCurrentThreadId` at `0x180002f06`
- `KERNEL32!LocalFree` at `0x1800030af`
- `KERNEL32!LocalFree` at `0x1800030bd`
- `KERNEL32!LocalFree` at `0x1800030af`
- `KERNEL32!LocalFree` at `0x1800030bd`
- `USER32!CloseDesktop` at `0x1800030cb`
- `USER32!CloseDesktop` at `0x1800030e7`
- `USER32!CloseDesktop` at `0x1800030cb`
- `USER32!CloseDesktop` at `0x1800030e7`
- `USER32!CreateDesktopA` at `0x180003026`
- `USER32!CreateDesktopA` at `0x180003026`
- `USER32!GetProcessWindowStation` at `0x180002f20`
- `USER32!GetProcessWindowStation` at `0x180002f20`
- `USER32!GetThreadDesktop` at `0x180002f0e`
- `USER32!GetThreadDesktop` at `0x180002f0e`
- `USER32!SetProcessWindowStation` at `0x180002f5a`
- `USER32!SetProcessWindowStation` at `0x180003090`
- `USER32!SetProcessWindowStation` at `0x180002f5a`
- `USER32!SetProcessWindowStation` at `0x180003090`
- `USER32!CreateWindowStationA` at `0x180002f45`
- `USER32!CreateWindowStationA` at `0x180002f45`
- `USER32!CloseWindowStation` at `0x1800030d9`
- `USER32!CloseWindowStation` at `0x1800030f5`
- `USER32!CloseWindowStation` at `0x1800030d9`
- `USER32!CloseWindowStation` at `0x1800030f5`
- `USER32!SetThreadDesktop` at `0x180003037`
- `USER32!SetThreadDesktop` at `0x18000309e`
- `USER32!SetThreadDesktop` at `0x180003037`
- `USER32!SetThreadDesktop` at `0x18000309e`

## pseudocode

```c
__int64 __fastcall InitDesktopWinsta(unsigned int a1, __int64 a2, __int64 a3, int a4)
{
  PACL v4; // r14
  HWINSTA v5; // r15
  HDESK v6; // r12
  HWINSTA ProcessWindowStation; // rdi
  HDESK ThreadDesktop; // rsi
  signed int v9; // ebx
  DWORD CurrentThreadId; // eax
  HWINSTA v11; // rax
  unsigned int v12; // ecx
  int v13; // r9d
  signed int LastError; // eax
  HDESK v15; // rax
  signed int v16; // eax
  PACL pDacl; // [rsp+30h] [rbp-50h] BYREF
  _SECURITY_ATTRIBUTES sa; // [rsp+38h] [rbp-48h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+70h] [rbp-10h]
  unsigned int v22; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v23; // [rsp+C8h] [rbp+48h] BYREF
  int v24; // [rsp+CCh] [rbp+4Ch]
  WELL_KNOWN_SID_TYPE v25; // [rsp+D0h] [rbp+50h] BYREF
  int v26; // [rsp+D4h] [rbp+54h]
  PACL v27; // [rsp+D8h] [rbp+58h] BYREF

  v25 = WinBuiltinAdministratorsSid;
  v21 = 0;
  pDacl = 0;
  v22 = 0;
  v23 = 983935;
  v4 = 0;
  v27 = 0;
  v5 = 0;
  v6 = 0;
  v26 = 1;
  ProcessWindowStation = 0;
  v24 = 131427;
  ThreadDesktop = 0;
  memset(&sa, 0, sizeof(sa));
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v9 = AllocateAndCreateWellKnownAcl(a1, &v25, &v23, a4, &pDacl, &v22);
  if ( v9 < 0 )
    goto LABEL_26;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    goto LABEL_16;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
    goto LABEL_16;
  sa.nLength = 24;
  sa.lpSecurityDescriptor = pSecurityDescriptor;
  sa.bInheritHandle = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( !ThreadDesktop )
    goto LABEL_16;
  ProcessWindowStation = GetProcessWindowStation();
  if ( !ProcessWindowStation )
    goto LABEL_16;
  v11 = CreateWindowStationA("__X78B95_89_IW", 0, 0xF037Fu, &sa);
  v5 = v11;
  if ( !v11 || !SetProcessWindowStation(v11) )
    goto LABEL_16;
  v25 = WinBuiltinAdministratorsSid;
  v23 = 983551;
  v26 = 1;
  v24 = 131523;
  v9 = AllocateAndCreateWellKnownAcl(v12, &v25, &v23, v13, &v27, &v22);
  if ( v9 >= 0 )
  {
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v4 = v27;
      goto LABEL_18;
    }
    v4 = v27;
    if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v27, 0) )
    {
      sa.nLength = 24;
      sa.lpSecurityDescriptor = pSecurityDescriptor;
      sa.bInheritHandle = 0;
      v15 = CreateDesktopA("__A8D9S1_42_ID", 0, 0, 0, 0xF01FFu, &sa);
      v6 = v15;
      if ( v15 )
      {
        if ( SetThreadDesktop(v15) )
        {
          g_hWinSta = v5;
          v5 = 0;
          g_hDesktop = v6;
          v6 = 0;
          g_hWinStaPrev = ProcessWindowStation;
          ProcessWindowStation = 0;
          g_hDesktopPrev = ThreadDesktop;
          ThreadDesktop = 0;
          goto LABEL_26;
        }
      }
    }
LABEL_16:
    v16 = GetLastError();
    v9 = v16;
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
LABEL_18:
    if ( v9 >= 0 )
      goto LABEL_26;
    if ( !ProcessWindowStation )
      goto LABEL_24;
    goto LABEL_23;
  }
  v4 = v27;
LABEL_23:
  SetProcessWindowStation(ProcessWindowStation);
LABEL_24:
  if ( ThreadDesktop )
    SetThreadDesktop(ThreadDesktop);
LABEL_26:
  if ( pDacl )
    LocalFree(pDacl);
  if ( v4 )
    LocalFree(v4);
  if ( v6 )
    CloseDesktop(v6);
  if ( v5 )
    CloseWindowStation(v5);
  if ( ThreadDesktop )
    CloseDesktop(ThreadDesktop);
  if ( ProcessWindowStation )
    CloseWindowStation(ProcessWindowStation);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002e34  push    rbp
0x180002e36  push    rbx
0x180002e37  push    rsi
0x180002e38  push    rdi
0x180002e39  push    r12
0x180002e3b  push    r14
0x180002e3d  push    r15
0x180002e3f  mov     rbp, rsp
0x180002e42  sub     rsp, 80h
0x180002e49  xor     eax, eax
0x180002e4b  mov     [rbp+arg_10], 1Ah
0x180002e52  mov     qword ptr [rbp+sa.bInheritHandle], rax
0x180002e56  lea     r8, [rbp+arg_8]; unsigned int *
0x180002e5a  mov     [rbp+var_10], rax
0x180002e5e  lea     rdx, [rbp+arg_10]; enum WELL_KNOWN_SID_TYPE *
0x180002e62  mov     [rbp+pDacl], rax
0x180002e66  xorps   xmm1, xmm1
0x180002e69  mov     [rbp+arg_0], eax
0x180002e6c  xorps   xmm0, xmm0
0x180002e6f  lea     rax, [rbp+arg_0]
0x180002e73  mov     [rbp+arg_8], 0F037Fh
0x180002e7a  mov     [rsp+80h+lpsa], rax; unsigned int *
0x180002e7f  xor     r14d, r14d
0x180002e82  lea     rax, [rbp+pDacl]
0x180002e86  mov     [rbp+arg_18], r14
0x180002e8a  mov     qword ptr [rsp+80h+dwDesiredAccess], rax; struct _ACL **
0x180002e8f  xor     r15d, r15d
0x180002e92  xor     r12d, r12d
0x180002e95  mov     [rbp+arg_14], 1
0x180002e9c  xor     edi, edi
0x180002e9e  mov     [rbp+arg_C], 20163h
0x180002ea5  xor     esi, esi
0x180002ea7  movups  xmmword ptr [rbp+sa.nLength], xmm0
0x180002eab  movups  [rbp+pSecurityDescriptor], xmm1
0x180002eaf  movups  [rbp+var_20], xmm1
0x180002eb3  call    ?AllocateAndCreateWellKnownAcl@@YAJKQEAW4WELL_KNOWN_SID_TYPE@@QEAKHPEAPEAU_ACL@@PEAK@Z; AllocateAndCreateWellKnownAcl(ulong,WELL_KNOWN_SID_TYPE * const,ulong * const,int,_ACL * *,ulong *)
0x180002eb8  mov     ebx, eax
0x180002eba  test    eax, eax
0x180002ebc  js      loc_1800030A4
0x180002ec2  lea     ebx, [rdi+1]
0x180002ec5  mov     edx, ebx; dwRevision
0x180002ec7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180002ecb  call    cs:__imp_InitializeSecurityDescriptor
0x180002ed1  test    eax, eax
0x180002ed3  jz      loc_180003041
0x180002ed9  mov     r8, [rbp+pDacl]; pDacl
0x180002edd  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180002ee1  xor     r9d, r9d; bDaclDefaulted
0x180002ee4  mov     edx, ebx; bDaclPresent
0x180002ee6  call    cs:__imp_SetSecurityDescriptorDacl
0x180002eec  test    eax, eax
0x180002eee  jz      loc_180003041
0x180002ef4  lea     rax, [rbp+pSecurityDescriptor]
0x180002ef8  mov     [rbp+sa.nLength], 18h
0x180002eff  mov     [rbp+sa.lpSecurityDescriptor], rax
0x180002f03  mov     [rbp+sa.bInheritHandle], esi
0x180002f06  call    cs:__imp_GetCurrentThreadId
0x180002f0c  mov     ecx, eax; dwThreadId
0x180002f0e  call    cs:__imp_GetThreadDesktop
0x180002f14  mov     rsi, rax
0x180002f17  test    rax, rax
0x180002f1a  jz      loc_180003041
0x180002f20  call    cs:__imp_GetProcessWindowStation
0x180002f26  mov     rdi, rax
0x180002f29  test    rax, rax
0x180002f2c  jz      loc_180003041
0x180002f32  lea     r9, [rbp+sa]; lpsa
0x180002f36  xor     edx, edx; dwFlags
0x180002f38  mov     r8d, 0F037Fh; dwDesiredAccess
0x180002f3e  lea     rcx, winsta; "__X78B95_89_IW"
0x180002f45  call    cs:__imp_CreateWindowStationA
0x180002f4b  mov     r15, rax
0x180002f4e  test    rax, rax
0x180002f51  jz      loc_180003041
0x180002f57  mov     rcx, rax; hWinSta
0x180002f5a  call    cs:__imp_SetProcessWindowStation
0x180002f60  test    eax, eax
0x180002f62  jz      loc_180003041
0x180002f68  lea     rax, [rbp+arg_0]
0x180002f6c  mov     [rbp+arg_10], 1Ah
0x180002f73  mov     [rsp+80h+lpsa], rax; unsigned int *
0x180002f78  lea     r8, [rbp+arg_8]; unsigned int *
0x180002f7c  lea     rax, [rbp+arg_18]
0x180002f80  mov     [rbp+arg_8], 0F01FFh
0x180002f87  lea     rdx, [rbp+arg_10]; enum WELL_KNOWN_SID_TYPE *
0x180002f8b  mov     qword ptr [rsp+80h+dwDesiredAccess], rax; struct _ACL **
0x180002f90  mov     [rbp+arg_14], ebx
0x180002f93  mov     [rbp+arg_C], 201C3h
0x180002f9a  call    ?AllocateAndCreateWellKnownAcl@@YAJKQEAW4WELL_KNOWN_SID_TYPE@@QEAKHPEAPEAU_ACL@@PEAK@Z; AllocateAndCreateWellKnownAcl(ulong,WELL_KNOWN_SID_TYPE * const,ulong * const,int,_ACL * *,ulong *)
0x180002f9f  mov     ebx, eax
0x180002fa1  test    eax, eax
0x180002fa3  js      loc_180003089
0x180002fa9  lea     edx, [r12+1]; dwRevision
0x180002fae  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180002fb2  call    cs:__imp_InitializeSecurityDescriptor
0x180002fb8  test    eax, eax
0x180002fba  jnz     short loc_180002FD7
0x180002fbc  call    cs:__imp_GetLastError
0x180002fc2  mov     ebx, eax
0x180002fc4  test    eax, eax
0x180002fc6  jle     short loc_180002FD1
0x180002fc8  movzx   ebx, ax
0x180002fcb  or      ebx, 80070000h
0x180002fd1  mov     r14, [rbp+arg_18]
0x180002fd5  jmp     short loc_180003056
0x180002fd7  mov     r14, [rbp+arg_18]
0x180002fdb  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180002fdf  xor     r9d, r9d; bDaclDefaulted
0x180002fe2  mov     r8, r14; pDacl
0x180002fe5  lea     edx, [r9+1]; bDaclPresent
0x180002fe9  call    cs:__imp_SetSecurityDescriptorDacl
0x180002fef  test    eax, eax
0x180002ff1  jz      short loc_180003041
0x180002ff3  lea     rax, [rbp+pSecurityDescriptor]
0x180002ff7  mov     [rbp+sa.nLength], 18h
0x180002ffe  mov     [rbp+sa.lpSecurityDescriptor], rax
0x180003002  lea     rcx, szDesktop; "__A8D9S1_42_ID"
0x180003009  lea     rax, [rbp+sa]
0x18000300d  mov     [rbp+sa.bInheritHandle], r12d
0x180003011  mov     [rsp+80h+lpsa], rax; lpsa
0x180003016  xor     r9d, r9d; dwFlags
0x180003019  xor     r8d, r8d; pDevmode
0x18000301c  mov     [rsp+80h+dwDesiredAccess], 0F01FFh; dwDesiredAccess
0x180003024  xor     edx, edx; lpszDevice
0x180003026  call    cs:__imp_CreateDesktopA
0x18000302c  mov     r12, rax
0x18000302f  test    rax, rax
0x180003032  jz      short loc_180003041
0x180003034  mov     rcx, rax; hDesktop
0x180003037  call    cs:__imp_SetThreadDesktop
0x18000303d  test    eax, eax
0x18000303f  jnz     short loc_180003061
0x180003041  call    cs:__imp_GetLastError
0x180003047  mov     ebx, eax
0x180003049  test    eax, eax
0x18000304b  jle     short loc_180003056
0x18000304d  movzx   ebx, ax
0x180003050  or      ebx, 80070000h
0x180003056  test    ebx, ebx
0x180003058  jns     short loc_1800030A4
0x18000305a  test    rdi, rdi
0x18000305d  jz      short loc_180003096
0x18000305f  jmp     short loc_18000308D
0x180003061  mov     cs:?g_hWinSta@@3PEAUHWINSTA__@@EA, r15; HWINSTA__ * g_hWinSta
0x180003068  xor     r15d, r15d
0x18000306b  mov     cs:?g_hDesktop@@3PEAUHDESK__@@EA, r12; HDESK__ * g_hDesktop
0x180003072  xor     r12d, r12d
0x180003075  mov     cs:?g_hWinStaPrev@@3PEAUHWINSTA__@@EA, rdi; HWINSTA__ * g_hWinStaPrev
0x18000307c  xor     edi, edi
0x18000307e  mov     cs:?g_hDesktopPrev@@3PEAUHDESK__@@EA, rsi; HDESK__ * g_hDesktopPrev
0x180003085  xor     esi, esi
0x180003087  jmp     short loc_1800030A4
0x180003089  mov     r14, [rbp+arg_18]
0x18000308d  mov     rcx, rdi; hWinSta
0x180003090  call    cs:__imp_SetProcessWindowStation
0x180003096  test    rsi, rsi
0x180003099  jz      short loc_1800030A4
0x18000309b  mov     rcx, rsi; hDesktop
0x18000309e  call    cs:__imp_SetThreadDesktop
0x1800030a4  cmp     [rbp+pDacl], 0
0x1800030a9  jz      short loc_1800030B5
0x1800030ab  mov     rcx, [rbp+pDacl]; hMem
0x1800030af  call    cs:__imp_LocalFree
0x1800030b5  test    r14, r14
0x1800030b8  jz      short loc_1800030C3
0x1800030ba  mov     rcx, r14; hMem
0x1800030bd  call    cs:__imp_LocalFree
0x1800030c3  test    r12, r12
0x1800030c6  jz      short loc_1800030D1
0x1800030c8  mov     rcx, r12; hDesktop
0x1800030cb  call    cs:__imp_CloseDesktop
0x1800030d1  test    r15, r15
0x1800030d4  jz      short loc_1800030DF
0x1800030d6  mov     rcx, r15; hWinSta
0x1800030d9  call    cs:__imp_CloseWindowStation
0x1800030df  test    rsi, rsi
0x1800030e2  jz      short loc_1800030ED
0x1800030e4  mov     rcx, rsi; hDesktop
0x1800030e7  call    cs:__imp_CloseDesktop
0x1800030ed  test    rdi, rdi
0x1800030f0  jz      short loc_1800030FB
0x1800030f2  mov     rcx, rdi; hWinSta
0x1800030f5  call    cs:__imp_CloseWindowStation
0x1800030fb  mov     eax, ebx
0x1800030fd  add     rsp, 80h
0x180003104  pop     r15
0x180003106  pop     r14
0x180003108  pop     r12
0x18000310a  pop     rdi
0x18000310b  pop     rsi
0x18000310c  pop     rbx
0x18000310d  pop     rbp
0x18000310e  retn
```
