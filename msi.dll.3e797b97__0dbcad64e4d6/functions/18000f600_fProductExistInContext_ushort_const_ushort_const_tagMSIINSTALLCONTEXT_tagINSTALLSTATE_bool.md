# fProductExistInContext(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,tagINSTALLSTATE &,bool &)

- ea: `0x18000f600`
- end: `0x18000f926`
- name: `?fProductExistInContext@@YA_NPEBG0W4tagMSIINSTALLCONTEXT@@AEAW4tagINSTALLSTATE@@AEA_N@Z`
- size: `806`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, enum tagINSTALLSTATE *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800e9668`
- `0x18021c1ac`

## callees

- `0x18000f600`
- `0x18000f930`
- `0x18003c030`
- `0x18003e40c`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000f73c`
- `ADVAPI32!RegCloseKey` at `0x18000f7d4`
- `ADVAPI32!RegCloseKey` at `0x18000f73c`
- `ADVAPI32!RegCloseKey` at `0x18000f7d4`
- `KERNEL32!InitializeCriticalSection` at `0x18000f677`
- `KERNEL32!InitializeCriticalSection` at `0x18000f677`
- `KERNEL32!DeleteCriticalSection` at `0x18000f768`
- `KERNEL32!DeleteCriticalSection` at `0x18000f800`
- `KERNEL32!DeleteCriticalSection` at `0x18000f768`
- `KERNEL32!DeleteCriticalSection` at `0x18000f800`
- `KERNEL32!LeaveCriticalSection` at `0x18000f758`
- `KERNEL32!LeaveCriticalSection` at `0x18000f7f0`
- `KERNEL32!LeaveCriticalSection` at `0x18000f758`
- `KERNEL32!LeaveCriticalSection` at `0x18000f7f0`
- `KERNEL32!EnterCriticalSection` at `0x18000f727`
- `KERNEL32!EnterCriticalSection` at `0x18000f7bf`
- `KERNEL32!EnterCriticalSection` at `0x18000f727`
- `KERNEL32!EnterCriticalSection` at `0x18000f7bf`
- `KERNEL32!GlobalFree` at `0x18000f77e`
- `KERNEL32!GlobalFree` at `0x18000f816`
- `KERNEL32!GlobalFree` at `0x18000f77e`
- `KERNEL32!GlobalFree` at `0x18000f816`

## pseudocode

```c
char __fastcall fProductExistInContext(
        const unsigned __int16 *a1,
        wchar_t *a2,
        enum tagMSIINSTALLCONTEXT a3,
        enum tagINSTALLSTATE *a4,
        bool *a5)
{
  unsigned int v9; // esi
  bool v10; // al
  unsigned __int32 v11; // ebx
  int v13; // [rsp+38h] [rbp-69h]
  int v14; // [rsp+38h] [rbp-69h]
  _DWORD v15[4]; // [rsp+50h] [rbp-51h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-41h] BYREF
  HGLOBAL hMem; // [rsp+70h] [rbp-31h]
  int v18; // [rsp+78h] [rbp-29h]
  __int16 v19; // [rsp+80h] [rbp-21h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+88h] [rbp-19h] BYREF

  *a4 = INSTALLSTATE_UNKNOWN;
  switch ( a3 )
  {
    case MSIINSTALLCONTEXT_MACHINE:
      v9 = 2;
      break;
    case MSIINSTALLCONTEXT_USERMANAGED:
      v9 = 0;
      break;
    case MSIINSTALLCONTEXT_USERUNMANAGED:
      v9 = 1;
      if ( !IsCurrentUser(a2) )
      {
        v10 = 1;
        goto LABEL_4;
      }
      break;
    default:
      v9 = 3;
      break;
  }
  v10 = 0;
LABEL_4:
  *a5 = v10;
  v18 = 1;
  hMem = &v19;
  *(_OWORD *)hKey = 0;
  v19 = 0;
  InitializeCriticalSection(&CriticalSection);
  v15[0] = 0;
  if ( !(unsigned int)GetInfo(a1, a2, v9, 1, L"LocalPackage", 0, v15, 1, -1) && v15[0] )
  {
    *a4 = INSTALLSTATE_DEFAULT;
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 1;
  }
  if ( *a5 )
    goto LABEL_32;
  if ( (a3 & 4) == 0 || (LOBYTE(v13) = 0, (unsigned int)GetInfo(a1, a2, 2, 1, L"AdvertiseFlags", 0, 0, v13, 1)) )
  {
    v11 = a3 & 0xFFFFFFFB;
    if ( !v11 )
    {
LABEL_9:
      EnterCriticalSection(&CriticalSection);
      if ( hKey[0] )
      {
        RegCloseKey(hKey[0]);
        hKey[0] = 0;
        *(_WORD *)hMem = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      DeleteCriticalSection(&CriticalSection);
      if ( v18 > 1 )
        GlobalFree(hMem);
      return 0;
    }
    LOBYTE(v13) = *a5;
    if ( (unsigned int)GetInfo(a1, a2, 0, 1, L"AdvertiseFlags", 0, 0, v13, 1) )
    {
      LOBYTE(v14) = *a5;
      if ( !(unsigned int)GetInfo(a1, a2, 1, 1, L"AdvertiseFlags", 0, 0, v14, 1) )
      {
        if ( (v11 & 2) == 0 )
          goto LABEL_9;
LABEL_22:
        *a4 = INSTALLSTATE_ADVERTISED;
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
        return 1;
      }
    }
    else if ( (v11 & 1) != 0 )
    {
      goto LABEL_22;
    }
LABEL_32:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
    return 0;
  }
  *a4 = INSTALLSTATE_ADVERTISED;
  EnterCriticalSection(&CriticalSection);
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    *(_WORD *)hMem = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( v18 > 1 )
    GlobalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x18000f600  mov     [rsp-8+arg_10], rbx
0x18000f605  push    rbp
0x18000f606  push    rsi
0x18000f607  push    rdi
0x18000f608  push    r12
0x18000f60a  push    r13
0x18000f60c  push    r14
0x18000f60e  push    r15
0x18000f610  lea     rbp, [rsp-1Fh]
0x18000f615  sub     rsp, 0C0h
0x18000f61c  mov     rax, cs:__security_cookie
0x18000f623  xor     rax, rsp
0x18000f626  mov     [rbp+4Fh+var_40], rax
0x18000f62a  mov     rdi, [rbp+4Fh+arg_20]
0x18000f62e  xor     r13d, r13d
0x18000f631  mov     dword ptr [r9], 0FFFFFFFFh
0x18000f638  mov     r14, r9
0x18000f63b  mov     ebx, r8d
0x18000f63e  mov     r15, rdx
0x18000f641  mov     r12, rcx
0x18000f644  cmp     r8d, 4
0x18000f648  jnz     loc_18000F8DA
0x18000f64e  mov     esi, 2
0x18000f653  xor     al, al
0x18000f655  mov     [rdi], al
0x18000f657  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f65b  lea     rax, [rbp+4Fh+var_70]
0x18000f65f  mov     [rbp+4Fh+var_78], 1
0x18000f666  xorps   xmm0, xmm0
0x18000f669  mov     [rbp+4Fh+hMem], rax
0x18000f66d  movdqa  xmmword ptr [rbp+4Fh+hKey], xmm0
0x18000f672  mov     [rbp+4Fh+var_70], r13w
0x18000f677  call    cs:__imp_InitializeCriticalSection
0x18000f67e  nop     dword ptr [rax+rax+00h]
0x18000f683  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x18000f68b  lea     rax, [rbp+4Fh+var_A0]
0x18000f68f  mov     [rsp+0F0h+var_B8], 1
0x18000f694  mov     r9d, 1
0x18000f69a  mov     [rsp+0F0h+var_C0], rax
0x18000f69f  mov     r8d, esi
0x18000f6a2  lea     rax, aLocalpackage_0; "LocalPackage"
0x18000f6a9  mov     [rsp+0F0h+var_C8], r13
0x18000f6ae  mov     rdx, r15
0x18000f6b1  mov     [rsp+0F0h+var_D0], rax
0x18000f6b6  mov     rcx, r12
0x18000f6b9  mov     [rbp+4Fh+var_A0], r13d
0x18000f6bd  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000f6c2  test    eax, eax
0x18000f6c4  jz      loc_18000F8B9
0x18000f6ca  cmp     [rdi], r13b
0x18000f6cd  jnz     loc_18000F918
0x18000f6d3  lea     rsi, aAdvertiseflags; "AdvertiseFlags"
0x18000f6da  test    bl, 4
0x18000f6dd  jz      short loc_18000F71A
0x18000f6df  mov     [rsp+0F0h+var_B0], 1
0x18000f6e7  mov     r9d, 1
0x18000f6ed  mov     [rsp+0F0h+var_B8], r13b
0x18000f6f2  mov     r8d, 2
0x18000f6f8  mov     [rsp+0F0h+var_C0], r13
0x18000f6fd  mov     rdx, r15
0x18000f700  mov     [rsp+0F0h+var_C8], r13
0x18000f705  mov     rcx, r12
0x18000f708  mov     [rsp+0F0h+var_D0], rsi
0x18000f70d  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000f712  test    eax, eax
0x18000f714  jz      loc_18000F7B4
0x18000f71a  and     ebx, 0FFFFFFFBh
0x18000f71d  jnz     loc_18000F829
0x18000f723  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f727  call    cs:__imp_EnterCriticalSection
0x18000f72e  nop     dword ptr [rax+rax+00h]
0x18000f733  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f737  test    rcx, rcx
0x18000f73a  jz      short loc_18000F754
0x18000f73c  call    cs:__imp_RegCloseKey
0x18000f743  nop     dword ptr [rax+rax+00h]
0x18000f748  mov     rax, [rbp+4Fh+hMem]
0x18000f74c  mov     [rbp+4Fh+hKey], r13
0x18000f750  mov     [rax], r13w
0x18000f754  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f758  call    cs:__imp_LeaveCriticalSection
0x18000f75f  nop     dword ptr [rax+rax+00h]
0x18000f764  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f768  call    cs:__imp_DeleteCriticalSection
0x18000f76f  nop     dword ptr [rax+rax+00h]
0x18000f774  cmp     [rbp+4Fh+var_78], 1
0x18000f778  jle     short loc_18000F78A
0x18000f77a  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18000f77e  call    cs:__imp_GlobalFree
0x18000f785  nop     dword ptr [rax+rax+00h]
0x18000f78a  xor     al, al
0x18000f78c  mov     rcx, [rbp+4Fh+var_40]
0x18000f790  xor     rcx, rsp; StackCookie
0x18000f793  call    __security_check_cookie
0x18000f798  mov     rbx, [rsp+0F0h+arg_10]
0x18000f7a0  add     rsp, 0C0h
0x18000f7a7  pop     r15
0x18000f7a9  pop     r14
0x18000f7ab  pop     r13
0x18000f7ad  pop     r12
0x18000f7af  pop     rdi
0x18000f7b0  pop     rsi
0x18000f7b1  pop     rbp
0x18000f7b2  retn
0x18000f7b4  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f7b8  mov     dword ptr [r14], 1
0x18000f7bf  call    cs:__imp_EnterCriticalSection
0x18000f7c6  nop     dword ptr [rax+rax+00h]
0x18000f7cb  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f7cf  test    rcx, rcx
0x18000f7d2  jz      short loc_18000F7EC
0x18000f7d4  call    cs:__imp_RegCloseKey
0x18000f7db  nop     dword ptr [rax+rax+00h]
0x18000f7e0  mov     rax, [rbp+4Fh+hMem]
0x18000f7e4  mov     [rbp+4Fh+hKey], r13
0x18000f7e8  mov     [rax], r13w
0x18000f7ec  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f7f0  call    cs:__imp_LeaveCriticalSection
0x18000f7f7  nop     dword ptr [rax+rax+00h]
0x18000f7fc  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000f800  call    cs:__imp_DeleteCriticalSection
0x18000f807  nop     dword ptr [rax+rax+00h]
0x18000f80c  cmp     [rbp+4Fh+var_78], 1
0x18000f810  jle     short loc_18000F822
0x18000f812  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18000f816  call    cs:__imp_GlobalFree
0x18000f81d  nop     dword ptr [rax+rax+00h]
0x18000f822  mov     al, 1
0x18000f824  jmp     loc_18000F78C
0x18000f829  movzx   eax, byte ptr [rdi]
0x18000f82c  mov     r9d, 1
0x18000f832  mov     [rsp+0F0h+var_B0], 1
0x18000f83a  xor     r8d, r8d
0x18000f83d  mov     [rsp+0F0h+var_B8], al
0x18000f841  mov     rdx, r15
0x18000f844  mov     [rsp+0F0h+var_C0], r13
0x18000f849  mov     rcx, r12
0x18000f84c  mov     [rsp+0F0h+var_C8], r13
0x18000f851  mov     [rsp+0F0h+var_D0], rsi
0x18000f856  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000f85b  test    eax, eax
0x18000f85d  jz      loc_18000F913
0x18000f863  movzx   eax, byte ptr [rdi]
0x18000f866  mov     r9d, 1
0x18000f86c  mov     [rsp+0F0h+var_B0], 1
0x18000f874  mov     r8d, r9d
0x18000f877  mov     [rsp+0F0h+var_B8], al
0x18000f87b  mov     rdx, r15
0x18000f87e  mov     [rsp+0F0h+var_C0], r13
0x18000f883  mov     rcx, r12
0x18000f886  mov     [rsp+0F0h+var_C8], r13
0x18000f88b  mov     [rsp+0F0h+var_D0], rsi
0x18000f890  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000f895  test    eax, eax
0x18000f897  jnz     short loc_18000F918
0x18000f899  test    bl, 2
0x18000f89c  jz      loc_18000F723
0x18000f8a2  lea     rcx, [rbp+4Fh+hKey]; this
0x18000f8a6  mov     dword ptr [r14], 1
0x18000f8ad  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18000f8b2  mov     al, 1
0x18000f8b4  jmp     loc_18000F78C
0x18000f8b9  cmp     [rbp+4Fh+var_A0], r13d
0x18000f8bd  jz      loc_18000F6CA
0x18000f8c3  lea     rcx, [rbp+4Fh+hKey]; this
0x18000f8c7  mov     dword ptr [r14], 5
0x18000f8ce  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18000f8d3  mov     al, 1
0x18000f8d5  jmp     loc_18000F78C
0x18000f8da  mov     ecx, ebx
0x18000f8dc  sub     ecx, 1
0x18000f8df  jz      short loc_18000F90B
0x18000f8e1  cmp     ecx, 1
0x18000f8e4  jnz     short loc_18000F901
0x18000f8e6  mov     esi, ecx
0x18000f8e8  mov     rcx, r15; String1
0x18000f8eb  call    ?IsCurrentUser@@YA_NPEBG@Z; IsCurrentUser(ushort const *)
0x18000f8f0  test    al, al
0x18000f8f2  jnz     loc_18000F653
0x18000f8f8  movzx   eax, sil
0x18000f8fc  jmp     loc_18000F655
0x18000f901  mov     esi, 3
0x18000f906  jmp     loc_18000F653
0x18000f90b  mov     esi, r13d
0x18000f90e  jmp     loc_18000F653
0x18000f913  test    bl, 1
0x18000f916  jnz     short loc_18000F8A2
0x18000f918  lea     rcx, [rbp+4Fh+hKey]; this
0x18000f91c  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18000f921  jmp     loc_18000F78A
```
