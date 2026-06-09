# GetInfoEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,bool,ushort const *,ushort *,ulong *)

- ea: `0x18001fd10`
- end: `0x18002040c`
- name: `?GetInfoEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@_N0PEAGPEAK@Z`
- size: `1788`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, bool, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001f700`
- `0x180179064`
- `0x18019ebb0`

## callees

- `0x180015950`
- `0x180017a84`
- `0x18001fd10`
- `0x180021030`
- `0x1800250d4`
- `0x180025a18`
- `0x180064a78`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002000f`
- `ADVAPI32!RegCloseKey` at `0x18002010e`
- `ADVAPI32!RegCloseKey` at `0x18002000f`
- `ADVAPI32!RegCloseKey` at `0x18002010e`
- `KERNEL32!InitializeCriticalSection` at `0x18001ff33`
- `KERNEL32!InitializeCriticalSection` at `0x18001ff33`
- `KERNEL32!DeleteCriticalSection` at `0x180020035`
- `KERNEL32!DeleteCriticalSection` at `0x180020134`
- `KERNEL32!DeleteCriticalSection` at `0x180020035`
- `KERNEL32!DeleteCriticalSection` at `0x180020134`
- `KERNEL32!LeaveCriticalSection` at `0x18002002b`
- `KERNEL32!LeaveCriticalSection` at `0x18002012a`
- `KERNEL32!LeaveCriticalSection` at `0x18002002b`
- `KERNEL32!LeaveCriticalSection` at `0x18002012a`
- `KERNEL32!EnterCriticalSection` at `0x18001ffff`
- `KERNEL32!EnterCriticalSection` at `0x1800200fe`
- `KERNEL32!EnterCriticalSection` at `0x18001ffff`
- `KERNEL32!EnterCriticalSection` at `0x1800200fe`
- `KERNEL32!lstrlenW` at `0x18001fdba`
- `KERNEL32!lstrlenW` at `0x18001fdba`
- `KERNEL32!GlobalFree` at `0x18001fe90`
- `KERNEL32!GlobalFree` at `0x180020045`
- `KERNEL32!GlobalFree` at `0x180020055`
- `KERNEL32!GlobalFree` at `0x1800200e8`
- `KERNEL32!GlobalFree` at `0x1800201aa`
- `KERNEL32!GlobalFree` at `0x180020313`
- `KERNEL32!GlobalFree` at `0x180020390`
- `KERNEL32!GlobalFree` at `0x1800203e6`
- `KERNEL32!GlobalFree` at `0x18001fe90`
- `KERNEL32!GlobalFree` at `0x180020045`
- `KERNEL32!GlobalFree` at `0x180020055`
- `KERNEL32!GlobalFree` at `0x1800200e8`
- `KERNEL32!GlobalFree` at `0x1800201aa`
- `KERNEL32!GlobalFree` at `0x180020313`
- `KERNEL32!GlobalFree` at `0x180020390`
- `KERNEL32!GlobalFree` at `0x1800203e6`
- `KERNEL32!lstrcmpiW` at `0x18002014d`
- `KERNEL32!lstrcmpiW` at `0x1800202b0`
- `KERNEL32!lstrcmpiW` at `0x1800202c8`
- `KERNEL32!lstrcmpiW` at `0x18002014d`
- `KERNEL32!lstrcmpiW` at `0x1800202b0`
- `KERNEL32!lstrcmpiW` at `0x1800202c8`
- `USER32!CharUpperW` at `0x18001fdb0`
- `USER32!CharUpperW` at `0x18001fdb0`

## string_xrefs

- `0x18001febd`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800200a8`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c
__int64 __fastcall GetInfoEx(
        WCHAR *a1,
        WCHAR *a2,
        enum tagMSIINSTALLCONTEXT a3,
        char a4,
        const unsigned __int16 *lpString1,
        unsigned __int16 *a6,
        unsigned int *a7)
{
  __int64 v10; // rax
  WCHAR *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  int v14; // eax
  char v16; // al
  _BYTE *v17; // r10
  int v18; // eax
  __int64 v19; // rcx
  unsigned __int16 *v20; // r9
  unsigned int v21; // r8d
  __int64 *v22; // rdx
  __int64 v23; // rax
  int v24; // esi
  int v25; // edi
  char v26; // bl
  unsigned int CurrentUserStringSID; // eax
  unsigned int v28; // ebx
  int v29; // edi
  unsigned int Info; // ebx
  _DWORD *v31; // rcx
  int v32; // r14d
  int v33; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v34; // [rsp+68h] [rbp-98h]
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+70h] [rbp-90h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+98h] [rbp-68h] BYREF
  HGLOBAL v37; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+CCh] [rbp-34h]
  _BYTE hMem[128]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR sz[37]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v42; // [rsp+19Ah] [rbp+9Ah]
  unsigned __int16 v43[40]; // [rsp+1A0h] [rbp+A0h] BYREF

  v34 = a7;
  if ( !a1 )
    return 87;
  v10 = 2147483646;
  v11 = sz;
  v12 = 39;
  do
  {
    if ( !v10 )
      break;
    if ( !*a1 )
      break;
    *v11++ = *a1++;
    --v10;
    --v12;
  }
  while ( v12 );
  v13 = v11 - 1;
  if ( v12 )
    v13 = v11;
  *v13 = 0;
  if ( !v12 )
    return 87;
  CharUpperW(sz);
  v14 = lstrlenW(sz);
  if ( v42 != 125
    || sz[9] != 45
    || sz[0] != 123
    || sz[24] != 45
    || v14 != 38
    || sz[14] != 45
    || sz[19] != 45
    || a2 && (a3 == MSIINSTALLCONTEXT_MACHINE || !*a2 || !lstrcmpiW(a2, L"S-1-5-18") || !lstrcmpiW(a2, L"S-1-1-0")) )
  {
    return 87;
  }
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0
    || a3 == (MSIINSTALLCONTEXT_USERUNMANAGED|MSIINSTALLCONTEXT_USERMANAGED)
    || !lpString1
    || !*lpString1
    || a6 && !a7 )
  {
    return 87;
  }
  v16 = 0;
  v38 = 64;
  v17 = hMem;
  v37 = hMem;
  if ( !a2 && (a3 & 3) != 0 )
  {
    v39 = 64;
    CurrentUserStringSID = GetCurrentUserStringSID(&v37);
    v28 = CurrentUserStringSID;
    if ( CurrentUserStringSID )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Failed to get the current user SID with error code=%d",
          (const unsigned __int16 *)CurrentUserStringSID,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( v38 > 64 )
        GlobalFree(v37);
      return v28;
    }
    v17 = v37;
    v16 = 1;
    a2 = (WCHAR *)v37;
  }
  if ( a3 != MSIINSTALLCONTEXT_MACHINE && !v16 )
  {
    if ( !IsCurrentUser(a2) && !IsAdmin() && !a4 )
    {
      if ( v38 > 64 )
        GlobalFree(v37);
      return 5;
    }
    v17 = v37;
  }
  v18 = 0;
  while ( v18 < 38 )
  {
    v19 = v18++;
    if ( !sz[v19] )
      goto LABEL_28;
  }
  if ( v42 != 125 || sz[0] != 123 )
    goto LABEL_28;
  v20 = v43;
  v21 = 0;
  v22 = qword_18026F6C0;
  while ( v22 < (__int64 *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData" )
  {
    if ( v21 >= 0x21 )
      goto LABEL_28;
    v23 = *(unsigned __int8 *)v22;
    v22 = (__int64 *)((char *)v22 + 1);
    *v20++ = sz[v23];
    ++v21;
  }
  if ( v21 >= 0x21 )
  {
LABEL_28:
    if ( v38 > 64 )
      GlobalFree(v17);
    return 87;
  }
  *v20 = 0;
  v24 = 3;
  switch ( a3 )
  {
    case MSIINSTALLCONTEXT_MACHINE:
      v25 = 2;
      break;
    case MSIINSTALLCONTEXT_USERMANAGED:
      v25 = 0;
      break;
    case MSIINSTALLCONTEXT_USERUNMANAGED:
      v25 = 1;
      if ( !IsCurrentUser(a2) )
      {
        v26 = 1;
        goto LABEL_40;
      }
      break;
    default:
      v25 = 3;
      break;
  }
  v26 = 0;
LABEL_40:
  LODWORD(hKey.LockSemaphore) = 1;
  hKey.OwningThread = &hKey.SpinCount;
  LOWORD(hKey.SpinCount) = 0;
  *(_OWORD *)&hKey.DebugInfo = 0;
  InitializeCriticalSection(&CriticalSection);
  v33 = 0;
  if ( (unsigned int)GetInfo(v43, a2, v25, 1, (__int64)L"LocalPackage", 0, &v33, 1, -1) || !v33 )
  {
    if ( !v26 )
    {
      if ( (a3 & 4) != 0 && !(unsigned int)GetInfo(v43, a2, 2, 1, (__int64)L"AdvertiseFlags", 0, 0, 0, 1) )
      {
        v29 = 1;
        EnterCriticalSection(&CriticalSection);
        if ( hKey.DebugInfo )
        {
          RegCloseKey((HKEY)hKey.DebugInfo);
          hKey.DebugInfo = 0;
          *(_WORD *)hKey.OwningThread = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        DeleteCriticalSection(&CriticalSection);
        if ( SLODWORD(hKey.LockSemaphore) > 1 )
          GlobalFree(hKey.OwningThread);
        goto LABEL_63;
      }
      if ( (a3 & 0xFFFFFFFB) == 0 )
      {
        EnterCriticalSection(&CriticalSection);
        if ( hKey.DebugInfo )
        {
          RegCloseKey((HKEY)hKey.DebugInfo);
          hKey.DebugInfo = 0;
          *(_WORD *)hKey.OwningThread = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        DeleteCriticalSection(&CriticalSection);
        if ( SLODWORD(hKey.LockSemaphore) > 1 )
          GlobalFree(hKey.OwningThread);
        goto LABEL_49;
      }
      if ( (unsigned int)GetInfo(v43, a2, 0, 1, (__int64)L"AdvertiseFlags", 0, 0, 0, 1) )
      {
        if ( (unsigned int)GetInfo(v43, a2, 1, 1, (__int64)L"AdvertiseFlags", 0, 0, 0, 1) || (a3 & 2) == 0 )
          goto LABEL_73;
LABEL_111:
        v29 = 1;
        goto LABEL_76;
      }
      if ( (a3 & 1) != 0 )
        goto LABEL_111;
    }
LABEL_73:
    CRegHandle::~CRegHandle(&hKey);
LABEL_49:
    if ( v38 > 64 )
      GlobalFree(v37);
    return 1605;
  }
  v29 = 5;
LABEL_76:
  CRegHandle::~CRegHandle(&hKey);
LABEL_63:
  if ( lstrcmpiW(lpString1, L"State") )
  {
    if ( a3 == MSIINSTALLCONTEXT_MACHINE )
    {
      v24 = 2;
    }
    else
    {
      v32 = a3 - 1;
      if ( v32 )
      {
        if ( v32 == 1 )
          v24 = 1;
      }
      else
      {
        v24 = 0;
      }
    }
    Info = GetInfo(v43, a2, v24, 1, (__int64)lpString1, (BYTE *)a6, v34, v26, v29);
    goto LABEL_67;
  }
  v31 = v34;
  if ( v34 )
  {
    if ( *v34 < 2u )
    {
      Info = 234;
    }
    else
    {
      *a6 = v29 + 48;
      Info = 0;
      a6[1] = 0;
    }
    *v31 = 1;
LABEL_67:
    if ( v38 > 64 )
      GlobalFree(v37);
    return Info;
  }
  if ( v38 > 64 )
    GlobalFree(v37);
  return 0;
}

```

## disassembly

```asm
0x18001fd10  push    rbp
0x18001fd12  push    rbx
0x18001fd13  push    rdi
0x18001fd14  push    r12
0x18001fd16  push    r13
0x18001fd18  push    r14
0x18001fd1a  push    r15
0x18001fd1c  lea     rbp, [rsp-100h]
0x18001fd24  sub     rsp, 200h
0x18001fd2b  mov     rax, cs:__security_cookie
0x18001fd32  xor     rax, rsp
0x18001fd35  mov     [rbp+130h+var_40], rax
0x18001fd3c  mov     rbx, [rbp+130h+arg_30]
0x18001fd43  movzx   edi, r9b
0x18001fd47  mov     r15, [rbp+130h+lpString1]
0x18001fd4e  mov     r14d, r8d
0x18001fd51  mov     r13, [rbp+130h+arg_28]
0x18001fd58  mov     r12, rdx
0x18001fd5b  mov     [rsp+230h+var_1C8], rbx
0x18001fd60  test    rcx, rcx
0x18001fd63  jz      short loc_18001FDCA
0x18001fd65  mov     eax, 7FFFFFFEh
0x18001fd6a  lea     r8, [rbp+130h+sz]
0x18001fd6e  mov     edx, 27h ; '''
0x18001fd73  test    rax, rax
0x18001fd76  jz      short loc_18001FD97
0x18001fd78  movzx   r9d, word ptr [rcx]
0x18001fd7c  test    r9w, r9w
0x18001fd80  jz      short loc_18001FD97
0x18001fd82  mov     [r8], r9w
0x18001fd86  add     rcx, 2
0x18001fd8a  add     r8, 2
0x18001fd8e  dec     rax
0x18001fd91  sub     rdx, 1
0x18001fd95  jnz     short loc_18001FD73
0x18001fd97  test    rdx, rdx
0x18001fd9a  lea     rcx, [r8-2]
0x18001fd9e  cmovnz  rcx, r8
0x18001fda2  xor     eax, eax
0x18001fda4  mov     [rcx], ax
0x18001fda7  test    rdx, rdx
0x18001fdaa  jz      short loc_18001FDCA
0x18001fdac  lea     rcx, [rbp+130h+sz]; lpsz
0x18001fdb0  call    cs:__imp_CharUpperW
0x18001fdb6  lea     rcx, [rbp+130h+sz]; lpString
0x18001fdba  call    cs:__imp_lstrlenW
0x18001fdc0  cmp     [rbp+130h+var_96], 7Dh ; '}'
0x18001fdc8  jz      short loc_18001FDF1
0x18001fdca  mov     eax, 57h ; 'W'
0x18001fdcf  mov     rcx, [rbp+130h+var_40]
0x18001fdd6  xor     rcx, rsp; StackCookie
0x18001fdd9  call    __security_check_cookie
0x18001fdde  add     rsp, 200h
0x18001fde5  pop     r15
0x18001fde7  pop     r14
0x18001fde9  pop     r13
0x18001fdeb  pop     r12
0x18001fded  pop     rdi
0x18001fdee  pop     rbx
0x18001fdef  pop     rbp
0x18001fdf0  retn
0x18001fdf1  cmp     [rbp+130h+var_CE], 2Dh ; '-'
0x18001fdf6  jnz     short loc_18001FDCA
0x18001fdf8  cmp     [rbp+130h+sz], 7Bh ; '{'
0x18001fdfd  jnz     short loc_18001FDCA
0x18001fdff  cmp     [rbp+130h+var_B0], 2Dh ; '-'
0x18001fe07  jnz     short loc_18001FDCA
0x18001fe09  cmp     eax, 26h ; '&'
0x18001fe0c  jnz     short loc_18001FDCA
0x18001fe0e  cmp     [rbp+130h+var_C4], 2Dh ; '-'
0x18001fe13  jnz     short loc_18001FDCA
0x18001fe15  cmp     [rbp+130h+var_BA], 2Dh ; '-'
0x18001fe1a  jnz     short loc_18001FDCA
0x18001fe1c  test    r12, r12
0x18001fe1f  jnz     loc_180020290
0x18001fe25  lea     eax, [r14-1]
0x18001fe29  test    eax, 0FFFFFFFCh
0x18001fe2e  jnz     short loc_18001FDCA
0x18001fe30  cmp     r14d, 3
0x18001fe34  jz      short loc_18001FDCA
0x18001fe36  test    r15, r15
0x18001fe39  jz      short loc_18001FDCA
0x18001fe3b  cmp     word ptr [r15], 0
0x18001fe40  jz      short loc_18001FDCA
0x18001fe42  test    r13, r13
0x18001fe45  jnz     loc_180020282
0x18001fe4b  xor     al, al
0x18001fe4d  mov     [rbp+130h+var_168], 40h ; '@'
0x18001fe54  lea     r10, [rbp+130h+hMem]
0x18001fe58  mov     [rbp+130h+var_170], r10
0x18001fe5c  test    r12, r12
0x18001fe5f  jz      loc_18002006D
0x18001fe65  cmp     r14d, 4
0x18001fe69  jnz     loc_1800202DB
0x18001fe6f  xor     eax, eax
0x18001fe71  cmp     eax, 26h ; '&'
0x18001fe74  jge     short loc_18001FE9B
0x18001fe76  movsxd  rcx, eax
0x18001fe79  inc     eax
0x18001fe7b  cmp     [rbp+rcx*2+130h+sz], 0
0x18001fe81  jnz     short loc_18001FE71
0x18001fe83  cmp     [rbp+130h+var_168], 40h ; '@'
0x18001fe87  jle     loc_18001FDCA
0x18001fe8d  mov     rcx, r10; hMem
0x18001fe90  call    cs:__imp_GlobalFree
0x18001fe96  jmp     loc_18001FDCA
0x18001fe9b  cmp     [rbp+130h+var_96], 7Dh ; '}'
0x18001fea3  jnz     short loc_18001FE83
0x18001fea5  cmp     [rbp+130h+sz], 7Bh ; '{'
0x18001feaa  jnz     short loc_18001FE83
0x18001feac  lea     r9, [rbp+130h+var_90]
0x18001feb3  xor     r8d, r8d
0x18001feb6  lea     rdx, qword_18026F6C0
0x18001febd  lea     r11, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001fec4  cmp     rdx, r11
0x18001fec7  jnb     short loc_18001FEE7
0x18001fec9  cmp     r8d, 21h ; '!'
0x18001fecd  jnb     short loc_18001FE83
0x18001fecf  movzx   eax, byte ptr [rdx]
0x18001fed2  inc     rdx
0x18001fed5  movzx   ecx, [rbp+rax*2+130h+sz]
0x18001feda  mov     [r9], cx
0x18001fede  add     r9, 2
0x18001fee2  inc     r8d
0x18001fee5  jmp     short loc_18001FEC4
0x18001fee7  cmp     r8d, 21h ; '!'
0x18001feeb  jnb     short loc_18001FE83
0x18001feed  xor     eax, eax
0x18001feef  mov     [rsp+230h+arg_10], rsi
0x18001fef7  mov     [r9], ax
0x18001fefb  mov     esi, 3
0x18001ff00  cmp     r14d, 4
0x18001ff04  jnz     loc_180020323
0x18001ff0a  mov     edi, 2
0x18001ff0f  xor     bl, bl
0x18001ff11  lea     rax, [rbp+130h+var_1A0]
0x18001ff15  mov     [rbp+130h+var_1A8], 1
0x18001ff1c  mov     [rbp+130h+var_1B0], rax
0x18001ff20  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18001ff24  xor     eax, eax
0x18001ff26  xorps   xmm0, xmm0
0x18001ff29  mov     [rbp+130h+var_1A0], ax
0x18001ff2d  movdqa  xmmword ptr [rsp+230h+hKey], xmm0
0x18001ff33  call    cs:__imp_InitializeCriticalSection
0x18001ff39  mov     dword ptr [rsp+230h+var_1F0], 0FFFFFFFFh
0x18001ff41  lea     rax, [rsp+230h+var_1D0]
0x18001ff46  mov     byte ptr [rsp+230h+var_1F8], 1
0x18001ff4b  lea     rcx, [rbp+130h+var_90]
0x18001ff52  mov     [rsp+230h+var_200], rax
0x18001ff57  mov     r9d, 1
0x18001ff5d  lea     rax, aLocalpackage_0; "LocalPackage"
0x18001ff64  mov     [rsp+230h+var_208], 0
0x18001ff6d  mov     r8d, edi
0x18001ff70  mov     [rsp+230h+var_210], rax
0x18001ff75  mov     rdx, r12
0x18001ff78  mov     [rsp+230h+var_1D0], 0
0x18001ff80  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18001ff85  test    eax, eax
0x18001ff87  jz      loc_180020263
0x18001ff8d  test    bl, bl
0x18001ff8f  jnz     loc_180020254
0x18001ff95  lea     rax, aAdvertiseflags; "AdvertiseFlags"
0x18001ff9c  test    r14b, 4
0x18001ffa0  jz      short loc_18001FFEF
0x18001ffa2  mov     dword ptr [rsp+230h+var_1F0], 1
0x18001ffaa  lea     rcx, [rbp+130h+var_90]
0x18001ffb1  mov     byte ptr [rsp+230h+var_1F8], bl
0x18001ffb5  mov     r9d, 1
0x18001ffbb  mov     [rsp+230h+var_200], 0
0x18001ffc4  mov     r8d, 2
0x18001ffca  mov     [rsp+230h+var_208], 0
0x18001ffd3  mov     rdx, r12
0x18001ffd6  mov     [rsp+230h+var_210], rax
0x18001ffdb  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18001ffe0  test    eax, eax
0x18001ffe2  jz      loc_1800200F5
0x18001ffe8  lea     rax, aAdvertiseflags; "AdvertiseFlags"
0x18001ffef  mov     edi, r14d
0x18001fff2  and     edi, 0FFFFFFFBh
0x18001fff5  jnz     loc_1800201BF
0x18001fffb  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18001ffff  call    cs:__imp_EnterCriticalSection
0x180020005  mov     rcx, [rsp+230h+hKey]; hKey
0x18002000a  test    rcx, rcx
0x18002000d  jz      short loc_180020027
0x18002000f  call    cs:__imp_RegCloseKey
0x180020015  mov     rax, [rbp+130h+var_1B0]
0x180020019  xor     ecx, ecx
0x18002001b  mov     [rsp+230h+hKey], 0
0x180020024  mov     [rax], cx
0x180020027  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18002002b  call    cs:__imp_LeaveCriticalSection
0x180020031  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x180020035  call    cs:__imp_DeleteCriticalSection
0x18002003b  cmp     [rbp+130h+var_1A8], 1
0x18002003f  jle     short loc_18002004B
0x180020041  mov     rcx, [rbp+130h+var_1B0]; hMem
0x180020045  call    cs:__imp_GlobalFree
0x18002004b  cmp     [rbp+130h+var_168], 40h ; '@'
0x18002004f  jle     short loc_18002005B
0x180020051  mov     rcx, [rbp+130h+var_170]; hMem
0x180020055  call    cs:__imp_GlobalFree
0x18002005b  mov     rsi, [rsp+230h+arg_10]
0x180020063  mov     eax, 645h
0x180020068  jmp     loc_18001FDCF
0x18002006d  test    r14b, 3
0x180020071  jz      loc_18001FE65
0x180020077  lea     rcx, [rbp+130h+var_170]
0x18002007b  mov     [rbp+130h+var_164], 40h ; '@'
0x180020082  call    ?GetCurrentUserStringSID@@YAKAEAV?$CAPITempBufferRef@G@@@Z; GetCurrentUserStringSID(CAPITempBufferRef<ushort> &)
0x180020087  mov     ebx, eax
0x180020089  test    eax, eax
0x18002008b  jz      loc_1800203C6
0x180020091  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180020098  jz      short loc_1800200DE
0x18002009a  lea     rax, aNull; "(NULL)"
0x1800200a1  xor     edx, edx; unsigned __int16
0x1800200a3  mov     [rsp+230h+var_1D8], rdx; void *
0x1800200a8  lea     r9, aFailedToGetThe; "Failed to get the current user SID with"...
0x1800200af  mov     [rsp+230h+var_1E0], edx; unsigned int
0x1800200b3  xor     r8d, r8d; int
0x1800200b6  mov     [rsp+230h+var_1E8], rax; unsigned __int16 *
0x1800200bb  mov     ecx, 9; int
0x1800200c0  mov     [rsp+230h+var_1F0], rax; unsigned __int16 *
0x1800200c5  mov     [rsp+230h+var_1F8], rax; unsigned __int16 *
0x1800200ca  mov     [rsp+230h+var_200], rax; unsigned __int16 *
0x1800200cf  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x1800200d4  mov     [rsp+230h+var_210], rbx; unsigned __int16 *
0x1800200d9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800200de  cmp     [rbp+130h+var_168], 40h ; '@'
0x1800200e2  jle     short loc_1800200EE
0x1800200e4  mov     rcx, [rbp+130h+var_170]; hMem
0x1800200e8  call    cs:__imp_GlobalFree
0x1800200ee  mov     eax, ebx
0x1800200f0  jmp     loc_18001FDCF
0x1800200f5  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x1800200f9  mov     edi, 1
0x1800200fe  call    cs:__imp_EnterCriticalSection
0x180020104  mov     rcx, [rsp+230h+hKey]; hKey
0x180020109  test    rcx, rcx
0x18002010c  jz      short loc_180020126
0x18002010e  call    cs:__imp_RegCloseKey
0x180020114  mov     rax, [rbp+130h+var_1B0]
0x180020118  xor     ecx, ecx
0x18002011a  mov     [rsp+230h+hKey], 0
0x180020123  mov     [rax], cx
0x180020126  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18002012a  call    cs:__imp_LeaveCriticalSection
0x180020130  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x180020134  call    cs:__imp_DeleteCriticalSection
0x18002013a  cmp     [rbp+130h+var_1A8], edi
0x18002013d  jg      loc_1800203E2
0x180020143  lea     rdx, aState; "State"
0x18002014a  mov     rcx, r15; lpString1
0x18002014d  call    cs:__imp_lstrcmpiW
0x180020153  test    eax, eax
0x180020155  jz      loc_180020353
0x18002015b  cmp     r14d, 4
0x18002015f  jnz     loc_1800203AE
0x180020165  mov     esi, 2
0x18002016a  mov     rcx, [rsp+230h+var_1C8]
0x18002016f  mov     r9d, 1
0x180020175  mov     dword ptr [rsp+230h+var_1F0], edi
0x180020179  mov     r8d, esi
0x18002017c  mov     byte ptr [rsp+230h+var_1F8], bl
0x180020180  mov     rdx, r12
0x180020183  mov     [rsp+230h+var_200], rcx
0x180020188  lea     rcx, [rbp+130h+var_90]
0x18002018f  mov     [rsp+230h+var_208], r13
0x180020194  mov     [rsp+230h+var_210], r15
0x180020199  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18002019e  mov     ebx, eax
0x1800201a0  cmp     [rbp+130h+var_168], 40h ; '@'
0x1800201a4  jle     short loc_1800201B0
0x1800201a6  mov     rcx, [rbp+130h+var_170]; hMem
0x1800201aa  call    cs:__imp_GlobalFree
0x1800201b0  mov     rsi, [rsp+230h+arg_10]
0x1800201b8  mov     eax, ebx
0x1800201ba  jmp     loc_18001FDCF
0x1800201bf  mov     dword ptr [rsp+230h+var_1F0], 1
0x1800201c7  lea     rcx, [rbp+130h+var_90]
0x1800201ce  mov     byte ptr [rsp+230h+var_1F8], 0
0x1800201d3  mov     r9d, 1
0x1800201d9  mov     [rsp+230h+var_200], 0
0x1800201e2  xor     r8d, r8d
0x1800201e5  mov     [rsp+230h+var_208], 0
0x1800201ee  mov     rdx, r12
0x1800201f1  mov     [rsp+230h+var_210], rax
0x1800201f6  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x1800201fb  test    eax, eax
0x1800201fd  jz      loc_1800203F1
0x180020203  mov     dword ptr [rsp+230h+var_1F0], 1
0x18002020b  lea     rax, aAdvertiseflags; "AdvertiseFlags"
0x180020212  mov     byte ptr [rsp+230h+var_1F8], 0
0x180020217  lea     rcx, [rbp+130h+var_90]
0x18002021e  mov     r9d, 1
0x180020224  mov     [rsp+230h+var_200], 0
0x18002022d  mov     [rsp+230h+var_208], 0
0x180020236  mov     r8d, r9d
0x180020239  mov     rdx, r12
  ... truncated ...
```
