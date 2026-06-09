# CDirectMusic::AddSoftwareSynths(void)

- ea: `0x180012e60`
- end: `0x180013044`
- name: `?AddSoftwareSynths@CDirectMusic@@QEAAJXZ`
- size: `484`
- prototype: `__int64 __fastcall(CDirectMusic *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013ed4`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x1800127d0`
- `0x180012e60`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180012f06`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180012f06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012f42`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012f42`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012f18`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180012f18`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180013005`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180013005`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180012edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180012edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013018`

## pseudocode

```c
__int64 __fastcall CDirectMusic::AddSoftwareSynths(CDirectMusic *this)
{
  DWORD v2; // ebx
  DWORD i; // edx
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  CLSID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  int v8; // [rsp+70h] [rbp-90h] BYREF
  CLSID v9; // [rsp+78h] [rbp-88h]
  int v10; // [rsp+8Ch] [rbp-74h]
  CHAR Name[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  OLECHAR sz[512]; // [rsp+2B0h] [rbp+1B0h] BYREF

  hKey = 0;
  pclsid = 0;
  memset_0(&v8, 0, 0x134u);
  ppv = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\DirectMusic\\SoftwareSynths", 0, 0x20019u, &hKey) )
  {
    v2 = 0;
    for ( i = 0; !RegEnumKeyA(hKey, i, Name, 0x100u); i = v2 )
    {
      _o_mbstowcs(sz, Name, 256);
      if ( CLSIDFromString(sz, &pclsid) >= 0 && CoCreateInstance(&pclsid, 0, 1u, &IID_IDirectMusicSynth, &ppv) >= 0 )
      {
        memset_0(&v8, 0, 0x134u);
        v8 = 308;
        v9 = pclsid;
        v10 = 1;
        if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 80LL))(ppv, &v8) >= 0 )
          CDirectMusic::AddDevice((__int64)this, (__int64)&v8, 2, -1, -1, -1, 0, 0, 0, 0);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ++v2;
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180012e60  mov     [rsp-8+arg_8], rbx
0x180012e65  mov     [rsp-8+arg_10], rdi
0x180012e6a  push    rbp
0x180012e6b  lea     rbp, [rsp-5C0h]
0x180012e73  sub     rsp, 6C0h
0x180012e7a  mov     rax, cs:__security_cookie
0x180012e81  xor     rax, rsp
0x180012e84  mov     [rbp+5C0h+var_10], rax
0x180012e8b  mov     rdi, rcx
0x180012e8e  mov     [rsp+6C0h+hKey], 0
0x180012e97  xorps   xmm0, xmm0
0x180012e9a  lea     rcx, [rsp+6C0h+var_650]; void *
0x180012e9f  xor     edx, edx; Val
0x180012ea1  mov     r8d, 134h; Size
0x180012ea7  movups  xmmword ptr [rsp+6C0h+pclsid.Data1], xmm0
0x180012eac  call    memset_0
0x180012eb1  lea     rax, [rsp+6C0h+hKey]
0x180012eb6  mov     [rsp+6C0h+ppv], 0
0x180012ebf  mov     r9d, 20019h; samDesired
0x180012ec5  mov     [rsp+6C0h+phkResult], rax; phkResult
0x180012eca  xor     r8d, r8d; ulOptions
0x180012ecd  lea     rdx, SubKey; "Software\\Microsoft\\DirectMusic\\Softw"...
0x180012ed4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012edb  call    cs:__imp_RegOpenKeyExA
0x180012ee1  test    eax, eax
0x180012ee3  jnz     loc_18001301E
0x180012ee9  xor     ebx, ebx
0x180012eeb  xor     edx, edx
0x180012eed  jmp     loc_180012FF3
0x180012ef2  mov     r8d, 100h
0x180012ef8  lea     rdx, [rbp+5C0h+Name]
0x180012eff  lea     rcx, [rbp+5C0h+sz]
0x180012f06  call    cs:__imp__o_mbstowcs
0x180012f0c  lea     rdx, [rsp+6C0h+pclsid]; pclsid
0x180012f11  lea     rcx, [rbp+5C0h+sz]; lpsz
0x180012f18  call    cs:__imp_CLSIDFromString
0x180012f1e  test    eax, eax
0x180012f20  js      loc_180012FEF
0x180012f26  xor     edx, edx; pUnkOuter
0x180012f28  lea     rax, [rsp+6C0h+ppv]
0x180012f2d  lea     r9, IID_IDirectMusicSynth; riid
0x180012f34  mov     [rsp+6C0h+phkResult], rax; ppv
0x180012f39  lea     rcx, [rsp+6C0h+pclsid]; rclsid
0x180012f3e  lea     r8d, [rdx+1]; dwClsContext
0x180012f42  call    cs:__imp_CoCreateInstance
0x180012f48  test    eax, eax
0x180012f4a  js      loc_180012FEF
0x180012f50  xor     edx, edx; Val
0x180012f52  lea     rcx, [rsp+6C0h+var_650]; void *
0x180012f57  mov     r8d, 134h; Size
0x180012f5d  call    memset_0
0x180012f62  movups  xmm0, xmmword ptr [rsp+6C0h+pclsid.Data1]
0x180012f67  mov     rcx, [rsp+6C0h+ppv]
0x180012f6c  lea     rdx, [rsp+6C0h+var_650]
0x180012f71  mov     [rsp+6C0h+var_650], 134h
0x180012f79  movdqu  [rsp+6C0h+var_648], xmm0
0x180012f7f  mov     [rbp+5C0h+var_634], 1
0x180012f86  mov     rax, [rcx]
0x180012f89  mov     rax, [rax+50h]
0x180012f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f92  test    eax, eax
0x180012f94  js      short loc_180012FDE
0x180012f96  mov     [rsp+6C0h+var_678], 0
0x180012f9f  lea     rdx, [rsp+6C0h+var_650]
0x180012fa4  mov     [rsp+6C0h+var_680], 0
0x180012fad  or      r9d, 0FFFFFFFFh
0x180012fb1  mov     [rsp+6C0h+var_688], 0
0x180012fba  mov     rcx, rdi
0x180012fbd  mov     [rsp+6C0h+var_690], 0
0x180012fc5  mov     [rsp+6C0h+var_698], 0FFFFFFFFh
0x180012fcd  lea     r8d, [r9+3]
0x180012fd1  mov     dword ptr [rsp+6C0h+phkResult], 0FFFFFFFFh
0x180012fd9  call    ?AddDevice@CDirectMusic@@QEAAJAEAU_DMUS_PORTCAPS@@W4PORTTYPE@@HHHHPEAUHKEY__@@PEAGPEAD@Z; CDirectMusic::AddDevice(_DMUS_PORTCAPS &,PORTTYPE,int,int,int,int,HKEY__ *,ushort *,char *)
0x180012fde  mov     rcx, [rsp+6C0h+ppv]
0x180012fe3  mov     rax, [rcx]
0x180012fe6  mov     rax, [rax+10h]
0x180012fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fef  inc     ebx
0x180012ff1  mov     edx, ebx; dwIndex
0x180012ff3  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180012ff8  lea     r8, [rbp+5C0h+Name]; lpName
0x180012fff  mov     r9d, 100h; cchName
0x180013005  call    cs:__imp_RegEnumKeyA
0x18001300b  test    eax, eax
0x18001300d  jz      loc_180012EF2
0x180013013  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180013018  call    cs:__imp_RegCloseKey
0x18001301e  xor     eax, eax
0x180013020  mov     rcx, [rbp+5C0h+var_10]
0x180013027  xor     rcx, rsp; StackCookie
0x18001302a  call    __security_check_cookie
0x18001302f  lea     r11, [rsp+6C0h+var_s0]
0x180013037  mov     rbx, [r11+18h]
0x18001303b  mov     rdi, [r11+20h]
0x18001303f  mov     rsp, r11
0x180013042  pop     rbp
0x180013043  retn
```
