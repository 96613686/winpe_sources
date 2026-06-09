# CFveApiBase::VolumeNameToDriveLetter(ushort const *,ushort *)

- ea: `0x180004d74`
- end: `0x1800050b6`
- name: `?VolumeNameToDriveLetter@CFveApiBase@@SAJPEBGPEAG@Z`
- size: `834`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x180049870`
- `0x180053b5c`

## callees

- `0x180004d74`
- `0x1800050c0`
- `0x180005410`
- `0x180005444`
- `0x18000ba30`
- `0x18000ca50`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180004dee`
- `ntdll!RtlSetThreadErrorMode` at `0x18000507a`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f173`
- `ntdll!RtlSetThreadErrorMode` at `0x180004dee`
- `ntdll!RtlSetThreadErrorMode` at `0x18000507a`
- `ntdll!RtlSetThreadErrorMode` at `0x18011f173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f51`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004f7a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180004f7a`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180004fd8`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180004fd8`

## pseudocode

```c
__int64 __fastcall CFveApiBase::VolumeNameToDriveLetter(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdi
  WCHAR *v4; // r14
  WCHAR *v5; // r13
  WCHAR *v6; // rsi
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  int LastHresultError; // ebx
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned __int64 v12; // r10
  __int64 v13; // rax
  WCHAR *v14; // rcx
  bool v15; // zf
  unsigned __int64 v16; // rcx
  WCHAR *v17; // rax
  WCHAR *v18; // rax
  unsigned int v19; // edx
  const unsigned __int16 *i; // rdi
  int v21; // eax
  __int64 v22; // rax
  unsigned __int16 v23; // ax
  unsigned __int16 v25; // [rsp+20h] [rbp-98h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-90h]
  WCHAR *v27; // [rsp+30h] [rbp-88h]
  WCHAR *v28; // [rsp+38h] [rbp-80h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v30; // [rsp+48h] [rbp-70h]
  __int64 v31; // [rsp+50h] [rbp-68h]
  unsigned __int16 *v32; // [rsp+58h] [rbp-60h]
  WCHAR *v33; // [rsp+60h] [rbp-58h]
  __int64 v34; // [rsp+68h] [rbp-50h]
  unsigned __int16 *v35; // [rsp+70h] [rbp-48h]
  DWORD cchBufferLength; // [rsp+78h] [rbp-40h] BYREF
  ULONG NewMode; // [rsp+7Ch] [rbp-3Ch] BYREF

  v35 = a2;
  v32 = a1;
  v3 = 0;
  v26 = 0;
  NewMode = 0;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v27 = 0;
  cchBufferLength = 260;
  v25 = 0;
  RtlSetThreadErrorMode(0x10u, &NewMode);
  if ( a1 )
  {
    v7 = 260;
    v31 = 260;
    v8 = a1;
    v30 = a1;
    LastHresultError = 0;
    while ( v7 && *v8 )
    {
      v30 = ++v8;
      v31 = --v7;
    }
    if ( !v7 )
      LastHresultError = -2147024809;
    if ( LastHresultError < 0 )
      v26 = 0;
    else
      v26 = 260 - v7;
    v3 = v26;
  }
  else
  {
    LastHresultError = -2147024809;
  }
  if ( LastHresultError < 0 )
  {
    v26 = 0;
    goto LABEL_51;
  }
  if ( v3 < 2 )
  {
    LastHresultError = -2147024809;
    goto LABEL_51;
  }
  v10 = v3 + 2;
  v11 = (unsigned __int16 *)CFveApiBase::FastAlloc(2 * v10);
  v4 = v11;
  v29 = v11;
  if ( !v11 )
    goto LABEL_18;
  LastHresultError = StringCchCopyW(v11, v10, v32);
  if ( LastHresultError >= 0 )
  {
    v13 = 260;
    v34 = 260;
    v14 = v4;
    v33 = v4;
    LastHresultError = v12;
    while ( 1 )
    {
      v15 = v13 == 0;
      if ( !v13 )
        break;
      if ( *v14 == (_WORD)v12 )
      {
        v15 = v13 == 0;
        break;
      }
      v33 = ++v14;
      v34 = --v13;
    }
    if ( v15 )
      LastHresultError = -2147024809;
    if ( LastHresultError < 0 )
      v26 = v12;
    else
      v26 = 260 - v13;
    if ( LastHresultError < 0 )
    {
      v26 = v12;
      goto LABEL_51;
    }
    v16 = v26;
    if ( v4[v26 - 1] != 92 )
    {
      v4[v26] = 92;
      v26 = v16 + 1;
      v4[v16 + 1] = v12;
    }
    v17 = (WCHAR *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, 0x64u);
    v5 = v17;
    v28 = v17;
    if ( v17 )
    {
      if ( !GetVolumeNameForVolumeMountPointW(v4, v17, 0x32u) )
      {
        LastHresultError = GetLastHresultError();
        goto LABEL_51;
      }
      while ( 1 )
      {
        if ( v6 )
        {
          CFveApiBase::FastFree(v6);
          v27 = 0;
        }
        v18 = (WCHAR *)CFveApiBase::FastAlloc(2LL * cchBufferLength);
        v6 = v18;
        v27 = v18;
        if ( !v18 )
          break;
        if ( GetVolumePathNamesForVolumeNameW(v5, v18, cchBufferLength, &cchBufferLength) )
        {
          for ( i = v6; *i; i += v22 + 1 )
          {
            v21 = CFveApiBase::CheckVolumeNameDriveLetter(i, v19, &v25);
            LastHresultError = v21;
            if ( v21 < 0 )
              goto LABEL_51;
            if ( !v21 )
              break;
            v22 = -1;
            do
              ++v22;
            while ( i[v22] );
          }
          v23 = v25;
          *v35 = v25;
          LastHresultError = v23 == 0;
          goto LABEL_51;
        }
        LastHresultError = GetLastHresultError();
        if ( LastHresultError != -2147024662 )
          goto LABEL_51;
      }
    }
LABEL_18:
    LastHresultError = -2147024882;
  }
LABEL_51:
  if ( v5 )
    CFveApiBase::FastFree(v5);
  if ( v4 )
    CFveApiBase::FastFree(v4);
  if ( v6 )
    CFveApiBase::FastFree(v6);
  RtlSetThreadErrorMode(NewMode, 0);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x180004d74  mov     r11, rsp
0x180004d77  mov     [r11+18h], rbx
0x180004d7b  mov     [r11+20h], rsi
0x180004d7f  push    rdi
0x180004d80  push    r12
0x180004d82  push    r13
0x180004d84  push    r14
0x180004d86  push    r15
0x180004d88  sub     rsp, 90h
0x180004d8f  mov     rax, cs:__security_cookie
0x180004d96  xor     rax, rsp
0x180004d99  mov     [rsp+0B8h+var_38], rax
0x180004da1  mov     [rsp+0B8h+var_48], rdx
0x180004da6  mov     rbx, rcx
0x180004da9  mov     [rsp+0B8h+var_60], rcx
0x180004dae  xor     r12d, r12d
0x180004db1  mov     edi, r12d
0x180004db4  mov     [rsp+0B8h+var_90], r12
0x180004db9  mov     [r11-3Ch], r12d
0x180004dbd  mov     r14d, r12d
0x180004dc0  mov     [r11-78h], r12
0x180004dc4  mov     r13d, r12d
0x180004dc7  mov     [r11-80h], r12
0x180004dcb  mov     esi, r12d
0x180004dce  mov     [rsp+0B8h+var_88], r12
0x180004dd3  mov     r15d, 104h
0x180004dd9  mov     [r11-40h], r15d
0x180004ddd  mov     eax, r12d
0x180004de0  mov     [rsp+0B8h+var_98], ax
0x180004de5  lea     rdx, [r11-3Ch]; OldMode
0x180004de9  lea     ecx, [r12+10h]; NewMode
0x180004dee  call    cs:__imp_RtlSetThreadErrorMode
0x180004df5  nop     dword ptr [rax+rax+00h]
0x180004dfa  nop
0x180004dfb  lea     rdx, [rsp+0B8h+var_90]
0x180004e00  xor     r10d, r10d
0x180004e03  test    rbx, rbx
0x180004e06  jz      short loc_180004E5F
0x180004e08  mov     ecx, r15d
0x180004e0b  mov     [rsp+0B8h+var_68], rcx
0x180004e10  mov     rax, rbx
0x180004e13  mov     [rsp+0B8h+var_70], rbx
0x180004e18  mov     ebx, r10d
0x180004e1b  test    rcx, rcx
0x180004e1e  jz      short loc_180004E39
0x180004e20  cmp     [rax], r10w
0x180004e24  jz      short loc_180004E39
0x180004e26  add     rax, 2
0x180004e2a  mov     [rsp+0B8h+var_70], rax
0x180004e2f  dec     rcx
0x180004e32  mov     [rsp+0B8h+var_68], rcx
0x180004e37  jmp     short loc_180004E1B
0x180004e39  mov     r12d, 80070057h
0x180004e3f  test    rcx, rcx
0x180004e42  cmovz   ebx, r12d
0x180004e46  test    ebx, ebx
0x180004e48  js      short loc_180004E55
0x180004e4a  mov     rax, r15
0x180004e4d  sub     rax, rcx
0x180004e50  mov     [rdx], rax
0x180004e53  jmp     short loc_180004E58
0x180004e55  mov     [rdx], r10
0x180004e58  mov     rdi, [rsp+0B8h+var_90]
0x180004e5d  jmp     short loc_180004E68
0x180004e5f  mov     r12d, 80070057h
0x180004e65  mov     ebx, r12d
0x180004e68  test    ebx, ebx
0x180004e6a  jns     short loc_180004E79
0x180004e6c  mov     [rdx], r10
0x180004e6f  mov     rdi, [rsp+0B8h+var_90]
0x180004e74  jmp     loc_18000504D
0x180004e79  cmp     rdi, 2
0x180004e7d  jnb     short loc_180004E87
0x180004e7f  mov     ebx, r12d
0x180004e82  jmp     loc_18000504D
0x180004e87  add     rdi, 2
0x180004e8b  lea     rcx, [rdi+rdi]; unsigned __int64
0x180004e8f  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x180004e94  mov     r14, rax
0x180004e97  mov     [rsp+0B8h+var_78], rax
0x180004e9c  xor     r10d, r10d
0x180004e9f  test    rax, rax
0x180004ea2  jnz     short loc_180004EAE
0x180004ea4  mov     ebx, 8007000Eh
0x180004ea9  jmp     loc_18000504D
0x180004eae  mov     r8, [rsp+0B8h+var_60]; unsigned __int16 *
0x180004eb3  mov     rdx, rdi; unsigned __int64
0x180004eb6  mov     rcx, r14; unsigned __int16 *
0x180004eb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004ebe  mov     ebx, eax
0x180004ec0  test    eax, eax
0x180004ec2  js      loc_18000504D
0x180004ec8  lea     rdx, [rsp+0B8h+var_90]
0x180004ecd  mov     rax, r15
0x180004ed0  mov     [rsp+0B8h+var_50], rax
0x180004ed5  mov     rcx, r14
0x180004ed8  mov     [rsp+0B8h+var_58], rcx
0x180004edd  mov     ebx, r10d
0x180004ee0  test    rax, rax
0x180004ee3  jz      short loc_180004F01
0x180004ee5  cmp     [rcx], r10w
0x180004ee9  jz      short loc_180004EFE
0x180004eeb  add     rcx, 2
0x180004eef  mov     [rsp+0B8h+var_58], rcx
0x180004ef4  dec     rax
0x180004ef7  mov     [rsp+0B8h+var_50], rax
0x180004efc  jmp     short loc_180004EE0
0x180004efe  test    rax, rax
0x180004f01  cmovz   ebx, r12d
0x180004f05  test    ebx, ebx
0x180004f07  js      short loc_180004F11
0x180004f09  sub     r15, rax
0x180004f0c  mov     [rdx], r15
0x180004f0f  jmp     short loc_180004F14
0x180004f11  mov     [rdx], r10
0x180004f14  test    ebx, ebx
0x180004f16  jns     short loc_180004F20
0x180004f18  mov     [rdx], r10
0x180004f1b  jmp     loc_18000504D
0x180004f20  mov     rcx, [rsp+0B8h+var_90]
0x180004f25  mov     eax, 5Ch ; '\'
0x180004f2a  cmp     [r14+rcx*2-2], ax
0x180004f30  jz      short loc_180004F44
0x180004f32  mov     [r14+rcx*2], ax
0x180004f37  inc     rcx
0x180004f3a  mov     [rsp+0B8h+var_90], rcx
0x180004f3f  mov     [r14+rcx*2], r10w
0x180004f44  xor     edx, edx; dwFlags
0x180004f46  lea     r8d, [rdx+64h]; dwBytes
0x180004f4a  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180004f51  call    cs:__imp_HeapAlloc
0x180004f58  nop     dword ptr [rax+rax+00h]
0x180004f5d  mov     r13, rax
0x180004f60  mov     [rsp+0B8h+var_80], rax
0x180004f65  test    rax, rax
0x180004f68  jz      loc_180004EA4
0x180004f6e  mov     r8d, 32h ; '2'; cchBufferLength
0x180004f74  mov     rdx, rax; lpszVolumeName
0x180004f77  mov     rcx, r14; lpszVolumeMountPoint
0x180004f7a  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180004f81  nop     dword ptr [rax+rax+00h]
0x180004f86  xor     r12d, r12d
0x180004f89  test    eax, eax
0x180004f8b  jnz     short loc_180004F99
0x180004f8d  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180004f92  mov     ebx, eax
0x180004f94  jmp     loc_18000504D
0x180004f99  test    rsi, rsi
0x180004f9c  jz      short loc_180004FAB
0x180004f9e  mov     rcx, rsi; lpMem
0x180004fa1  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180004fa6  mov     [rsp+0B8h+var_88], r12
0x180004fab  mov     ecx, [rsp+0B8h+cchBufferLength]
0x180004faf  add     rcx, rcx; unsigned __int64
0x180004fb2  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x180004fb7  mov     rsi, rax
0x180004fba  mov     [rsp+0B8h+var_88], rax
0x180004fbf  test    rax, rax
0x180004fc2  jz      loc_180004EA4
0x180004fc8  lea     r9, [rsp+0B8h+cchBufferLength]; lpcchReturnLength
0x180004fcd  mov     r8d, [rsp+0B8h+cchBufferLength]; cchBufferLength
0x180004fd2  mov     rdx, rax; lpszVolumePathNames
0x180004fd5  mov     rcx, r13; lpszVolumeName
0x180004fd8  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180004fdf  nop     dword ptr [rax+rax+00h]
0x180004fe4  xor     r10d, r10d
0x180004fe7  test    eax, eax
0x180004fe9  jnz     short loc_180004FFE
0x180004feb  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180004ff0  mov     ebx, eax
0x180004ff2  cmp     eax, 800700EAh
0x180004ff7  jnz     short loc_18000504D
0x180004ff9  xor     r12d, r12d
0x180004ffc  jmp     short loc_180004F99
0x180004ffe  mov     rdi, rsi
0x180005001  cmp     [rdi], r10w
0x180005005  jz      short loc_180005037
0x180005007  lea     r8, [rsp+0B8h+var_98]; unsigned __int16 *
0x18000500c  mov     rcx, rdi; unsigned __int16 *
0x18000500f  call    ?CheckVolumeNameDriveLetter@CFveApiBase@@SAJPEBGKPEAG@Z; CFveApiBase::CheckVolumeNameDriveLetter(ushort const *,ulong,ushort *)
0x180005014  mov     ebx, eax
0x180005016  xor     r10d, r10d
0x180005019  test    eax, eax
0x18000501b  js      short loc_18000504D
0x18000501d  jz      short loc_180005037
0x18000501f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005023  inc     rax
0x180005026  cmp     [rdi+rax*2], r10w
0x18000502b  jnz     short loc_180005023
0x18000502d  lea     rdi, [rdi+rax*2]
0x180005031  add     rdi, 2
0x180005035  jmp     short loc_180005001
0x180005037  movzx   eax, [rsp+0B8h+var_98]
0x18000503c  mov     rcx, [rsp+0B8h+var_48]
0x180005041  mov     [rcx], ax
0x180005044  mov     ebx, r10d
0x180005047  test    ax, ax
0x18000504a  setz    bl
0x18000504d  test    r13, r13
0x180005050  jz      short loc_18000505A
0x180005052  mov     rcx, r13; lpMem
0x180005055  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000505a  test    r14, r14
0x18000505d  jz      short loc_180005067
0x18000505f  mov     rcx, r14; lpMem
0x180005062  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180005067  test    rsi, rsi
0x18000506a  jz      short loc_180005074
0x18000506c  mov     rcx, rsi; lpMem
0x18000506f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180005074  xor     edx, edx; OldMode
0x180005076  mov     ecx, [rsp+0B8h+NewMode]; NewMode
0x18000507a  call    cs:__imp_RtlSetThreadErrorMode
0x180005081  nop     dword ptr [rax+rax+00h]
0x180005086  mov     eax, ebx
0x180005088  mov     rcx, [rsp+0B8h+var_38]
0x180005090  xor     rcx, rsp; StackCookie
0x180005093  call    __security_check_cookie
0x180005098  lea     r11, [rsp+0B8h+var_28]
0x1800050a0  mov     rbx, [r11+40h]
0x1800050a4  mov     rsi, [r11+48h]
0x1800050a8  mov     rsp, r11
0x1800050ab  pop     r15
0x1800050ad  pop     r14
0x1800050af  pop     r13
0x1800050b1  pop     r12
0x1800050b3  pop     rdi
0x1800050b4  retn
0x18011f123  push    rbp
0x18011f125  sub     rsp, 20h
0x18011f129  mov     rbp, rdx
0x18011f12c  mov     rcx, [rbp+38h]; lpMem
0x18011f130  test    rcx, rcx
0x18011f133  jz      short loc_18011F142
0x18011f135  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f13a  mov     qword ptr [rbp+38h], 0
0x18011f142  mov     rcx, [rbp+40h]; lpMem
0x18011f146  test    rcx, rcx
0x18011f149  jz      short loc_18011F158
0x18011f14b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f150  mov     qword ptr [rbp+40h], 0
0x18011f158  mov     rcx, [rbp+30h]; lpMem
0x18011f15c  test    rcx, rcx
0x18011f15f  jz      short loc_18011F16E
0x18011f161  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f166  mov     qword ptr [rbp+30h], 0
0x18011f16e  xor     edx, edx; OldMode
0x18011f170  mov     ecx, [rbp+7Ch]; NewMode
0x18011f173  call    cs:__imp_RtlSetThreadErrorMode
0x18011f17a  nop     dword ptr [rax+rax+00h]
0x18011f17f  nop
0x18011f180  add     rsp, 20h
0x18011f184  pop     rbp
0x18011f185  retn
```
