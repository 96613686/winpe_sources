# HyperVStorage::HyperVStorage(void)

- ea: `0x18006e080`
- end: `0x18006e3d9`
- name: `??0HyperVStorage@@QEAA@XZ`
- size: `857`
- prototype: `HyperVStorage *__fastcall(HyperVStorage *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180061030`

## callees

- `0x1800067c0`
- `0x1800067e4`
- `0x1800277ac`
- `0x18006e080`
- `0x1800788c4`
- `0x180088c4c`
- `0x18008c614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006e136`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006e136`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006e35f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006e35f`
- `RPCRT4!UuidCreate` at `0x18006e391`
- `RPCRT4!UuidCreate` at `0x18006e391`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18006e2b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18006e2b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HyperVStorage *__fastcall HyperVStorage::HyperVStorage(HyperVStorage *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  struct _FILETIME v9; // rdx
  struct _GUID v11; // [rsp+20h] [rbp-58h] BYREF
  HyperVStorage *v12; // [rsp+30h] [rbp-48h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-40h] BYREF

  v12 = this;
  *(_QWORD *)this = &HyperVStorage::`vftable'{for `HyperVStorageServices'};
  *((_QWORD *)this + 1) = &HyperVStorage::`vftable'{for `HyperVStorageOperationsInterface'};
  *((_QWORD *)this + 2) = &HyperVStorage::`vftable'{for `HyperVStorageChangeTrackingInterface'};
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 54) = 0;
  *((_BYTE *)this + 70) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v2 = operator new(0x68u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)this + 15) = v2;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 44) = 0;
  InitializeSRWLock((PSRWLOCK)this + 21);
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  v3 = operator new(0x28u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)this + 26) = v3;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  v4 = operator new(0x28u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)this + 28) = v4;
  *((_DWORD *)this + 60) = 4096;
  *((_QWORD *)this + 31) = (char *)this + 320;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *((_QWORD *)this + 33) = v5;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_WORD *)this + 204) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  v6 = operator new(0x28u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *((_QWORD *)this + 52) = v6;
  *(_QWORD *)&v11.Data1 = (char *)this + 432;
  *((_DWORD *)this + 108) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  v7 = operator new(0x4B8u);
  *v7 = v7;
  v7[1] = v7;
  *((_QWORD *)this + 55) = v7;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 7;
  *((_QWORD *)this + 61) = 8;
  *((_DWORD *)this + 108) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    (char *)this + 456,
    16,
    *((_QWORD *)this + 55));
  *((_QWORD *)this + 62) = 0;
  QueryPerformanceFrequency((LARGE_INTEGER *)this + 63);
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  v8 = operator new(0x30u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *((_QWORD *)this + 64) = v8;
  *((_QWORD *)this + 66) = this;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_WORD *)this + 76) = 0;
  *(_QWORD *)((char *)this + 321) = 0;
  *(_QWORD *)((char *)this + 329) = 0;
  *(_QWORD *)((char *)this + 337) = 0;
  *(_QWORD *)((char *)this + 345) = 0;
  *((_BYTE *)this + 320) = 9;
  *(_DWORD *)((char *)this + 322) = 33;
  *((_BYTE *)this + 340) = 0;
  if ( *((_QWORD *)this + 31) )
    *(_DWORD *)(*((_QWORD *)this + 31) + 12LL) = HyperVStorageKeyTableEntry::CalculateChecksum((HyperVStorage *)((char *)this + 248));
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v9 = SystemTimeAsFileTime;
  *(struct _FILETIME *)((char *)this + 356) = SystemTimeAsFileTime;
  *(struct _FILETIME *)((char *)this + 364) = v9;
  HyperVStoragePerfTracker::NewInstance((HyperVStorage *)((char *)this + 432), L"GlobalInstance");
  UuidCreate((UUID *)((char *)this + 568));
  v11 = *(struct _GUID *)((char *)this + 568);
  HyperVStorageTrace::StorageCreated(&v11, SystemTimeAsFileTime);
  return this;
}

```

## disassembly

```asm
0x18006e080  mov     [rsp+arg_8], rbx
0x18006e085  mov     [rsp+arg_10], rbp
0x18006e08a  push    rsi
0x18006e08b  push    rdi
0x18006e08c  push    r13
0x18006e08e  push    r14
0x18006e090  push    r15
0x18006e092  sub     rsp, 50h
0x18006e096  mov     rax, cs:__security_cookie
0x18006e09d  xor     rax, rsp
0x18006e0a0  mov     [rsp+78h+var_38], rax
0x18006e0a5  mov     rsi, rcx
0x18006e0a8  mov     [rsp+78h+var_48], rcx
0x18006e0ad  lea     rax, ??_7HyperVStorage@@6BHyperVStorageServices@@@; const HyperVStorage::`vftable'{for `HyperVStorageServices'}
0x18006e0b4  mov     [rcx], rax
0x18006e0b7  lea     rax, ??_7HyperVStorage@@6BHyperVStorageOperationsInterface@@@; const HyperVStorage::`vftable'{for `HyperVStorageOperationsInterface'}
0x18006e0be  mov     [rcx+8], rax
0x18006e0c2  lea     rax, ??_7HyperVStorage@@6BHyperVStorageChangeTrackingInterface@@@; const HyperVStorage::`vftable'{for `HyperVStorageChangeTrackingInterface'}
0x18006e0c9  mov     [rcx+10h], rax
0x18006e0cd  xorps   xmm0, xmm0
0x18006e0d0  movups  xmmword ptr [rcx+18h], xmm0
0x18006e0d4  movups  xmmword ptr [rcx+28h], xmm0
0x18006e0d8  movups  xmmword ptr [rcx+36h], xmm0
0x18006e0dc  xor     r13d, r13d
0x18006e0df  mov     [rcx+46h], r13b
0x18006e0e3  mov     [rcx+48h], r13
0x18006e0e7  mov     [rcx+50h], r13
0x18006e0eb  mov     [rcx+58h], r13
0x18006e0ef  mov     [rcx+60h], r13
0x18006e0f3  mov     [rcx+68h], r13
0x18006e0f7  mov     [rcx+70h], r13
0x18006e0fb  mov     [rcx+78h], r13
0x18006e0ff  mov     [rcx+80h], r13
0x18006e106  lea     ecx, [r13+68h]; Size
0x18006e10a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e10f  mov     [rax], rax
0x18006e112  mov     [rax+8], rax
0x18006e116  mov     [rax+10h], rax
0x18006e11a  mov     word ptr [rax+18h], 101h
0x18006e120  mov     [rsi+78h], rax
0x18006e124  mov     [rsi+0A0h], r13
0x18006e12b  lea     rcx, [rsi+0A8h]; SRWLock
0x18006e132  mov     [rcx+8], r13d
0x18006e136  call    cs:__imp_InitializeSRWLock
0x18006e13c  mov     [rsi+0B8h], r13
0x18006e143  mov     [rsi+0C0h], r13
0x18006e14a  mov     [rsi+0C8h], r13
0x18006e151  lea     rbx, [rsi+0D0h]
0x18006e158  mov     [rbx], r13
0x18006e15b  mov     [rbx+8], r13
0x18006e15f  lea     ebp, [r13+28h]
0x18006e163  mov     ecx, ebp; Size
0x18006e165  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e16a  mov     [rax], rax
0x18006e16d  mov     [rax+8], rax
0x18006e171  mov     [rax+10h], rax
0x18006e175  mov     word ptr [rax+18h], 101h
0x18006e17b  mov     [rbx], rax
0x18006e17e  lea     rbx, [rsi+0E0h]
0x18006e185  mov     [rbx], r13
0x18006e188  mov     [rbx+8], r13
0x18006e18c  mov     ecx, ebp; Size
0x18006e18e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e193  mov     [rax], rax
0x18006e196  mov     [rax+8], rax
0x18006e19a  mov     [rax+10h], rax
0x18006e19e  mov     word ptr [rax+18h], 101h
0x18006e1a4  mov     [rbx], rax
0x18006e1a7  mov     dword ptr [rsi+0F0h], 1000h
0x18006e1b1  lea     r14, [rsi+0F8h]
0x18006e1b8  lea     rdi, [rsi+140h]
0x18006e1bf  mov     [r14], rdi
0x18006e1c2  mov     [r14+8], r13
0x18006e1c6  mov     [r14+10h], r13
0x18006e1ca  mov     [r14+18h], r13
0x18006e1ce  lea     ecx, [rbp+8]; Size
0x18006e1d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e1d6  mov     [rax], rax
0x18006e1d9  mov     [rax+8], rax
0x18006e1dd  mov     [rax+10h], rax
0x18006e1e1  mov     word ptr [rax+18h], 101h
0x18006e1e7  mov     [r14+10h], rax
0x18006e1eb  mov     [r14+20h], r13
0x18006e1ef  mov     [r14+28h], r13
0x18006e1f3  mov     [r14+30h], r13
0x18006e1f7  mov     [r14+38h], r13
0x18006e1fb  mov     [r14+40h], r13
0x18006e1ff  mov     [rsi+178h], r13
0x18006e206  mov     [rsi+180h], r13
0x18006e20d  mov     [rsi+188h], r13
0x18006e214  mov     [rsi+190h], r13
0x18006e21b  mov     [rsi+198h], r13w
0x18006e223  lea     rbx, [rsi+1A0h]
0x18006e22a  mov     [rbx], r13
0x18006e22d  mov     [rbx+8], r13
0x18006e231  mov     ecx, ebp; Size
0x18006e233  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e238  mov     [rax], rax
0x18006e23b  mov     [rax+8], rax
0x18006e23f  mov     [rax+10h], rax
0x18006e243  mov     word ptr [rax+18h], 101h
0x18006e249  mov     [rbx], rax
0x18006e24c  lea     r15, [rsi+1B0h]
0x18006e253  mov     qword ptr [rsp+78h+var_58.Data1], r15
0x18006e258  mov     [r15], r13d
0x18006e25b  mov     [r15+8], r13
0x18006e25f  mov     [r15+10h], r13
0x18006e263  mov     ecx, 4B8h; Size
0x18006e268  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e26d  mov     [rax], rax
0x18006e270  mov     [rax+8], rax
0x18006e274  mov     [r15+8], rax
0x18006e278  lea     rcx, [r15+18h]
0x18006e27c  mov     [rcx], r13
0x18006e27f  mov     [rcx+8], r13
0x18006e283  mov     [rcx+10h], r13
0x18006e287  mov     qword ptr [r15+30h], 7
0x18006e28f  mov     qword ptr [r15+38h], 8
0x18006e297  mov     dword ptr [r15], 3F800000h
0x18006e29e  mov     r8, [r15+8]
0x18006e2a2  lea     edx, [rbp-18h]
0x18006e2a5  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18006e2aa  nop
0x18006e2ab  xor     eax, eax
0x18006e2ad  mov     [r15+40h], rax
0x18006e2b1  lea     rcx, [r15+48h]; lpFrequency
0x18006e2b5  call    cs:__imp_QueryPerformanceFrequency
0x18006e2bb  nop
0x18006e2bc  lea     rbx, [rsi+200h]
0x18006e2c3  mov     [rbx], r13
0x18006e2c6  mov     [rbx+8], r13
0x18006e2ca  lea     ecx, [rbp+8]; Size
0x18006e2cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e2d2  mov     [rax], rax
0x18006e2d5  mov     [rax+8], rax
0x18006e2d9  mov     [rax+10h], rax
0x18006e2dd  mov     word ptr [rax+18h], 101h
0x18006e2e3  mov     [rbx], rax
0x18006e2e6  mov     [rsi+210h], rsi
0x18006e2ed  mov     [rsi+218h], r13
0x18006e2f4  mov     [rsi+220h], r13
0x18006e2fb  mov     [rsi+228h], r13
0x18006e302  mov     [rsi+230h], r13
0x18006e309  xorps   xmm0, xmm0
0x18006e30c  xor     eax, eax
0x18006e30e  movups  xmmword ptr [rsi+88h], xmm0
0x18006e315  mov     [rsi+98h], ax
0x18006e31c  mov     [rdi+1], r13
0x18006e320  mov     [rdi+9], r13
0x18006e324  mov     [rdi+11h], r13
0x18006e328  mov     [rdi+19h], r13
0x18006e32c  mov     byte ptr [rdi], 9
0x18006e32f  mov     dword ptr [rsi+142h], 21h ; '!'
0x18006e339  mov     [rsi+154h], r13b
0x18006e340  cmp     [r14], r13
0x18006e343  jz      short loc_18006E355
0x18006e345  mov     rcx, r14; this
0x18006e348  call    ?CalculateChecksum@HyperVStorageKeyTableEntry@@AEBAIXZ; HyperVStorageKeyTableEntry::CalculateChecksum(void)
0x18006e34d  mov     edx, eax
0x18006e34f  mov     rax, [r14]
0x18006e352  mov     [rax+0Ch], edx
0x18006e355  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18006e35a  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006e35f  call    cs:__imp_GetSystemTimeAsFileTime
0x18006e365  mov     rdx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x18006e36a  mov     [rsi+164h], rdx
0x18006e371  mov     [rsi+16Ch], rdx
0x18006e378  lea     rdx, aGlobalinstance; "GlobalInstance"
0x18006e37f  mov     rcx, r15; this
0x18006e382  call    ?NewInstance@HyperVStoragePerfTracker@@QEAAXPEBG@Z; HyperVStoragePerfTracker::NewInstance(ushort const *)
0x18006e387  lea     rbx, [rsi+238h]
0x18006e38e  mov     rcx, rbx; Uuid
0x18006e391  call    cs:__imp_UuidCreate
0x18006e397  movups  xmm0, xmmword ptr [rbx]
0x18006e39a  movdqu  xmmword ptr [rsp+78h+var_58.Data1], xmm0
0x18006e3a0  mov     rdx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18006e3a5  lea     rcx, [rsp+78h+var_58]; struct _GUID
0x18006e3aa  call    ?StorageCreated@HyperVStorageTrace@@SAXU_GUID@@U_FILETIME@@@Z; HyperVStorageTrace::StorageCreated(_GUID,_FILETIME)
0x18006e3af  nop
0x18006e3b0  mov     rax, rsi
0x18006e3b3  mov     rcx, [rsp+78h+var_38]
0x18006e3b8  xor     rcx, rsp; StackCookie
0x18006e3bb  call    __security_check_cookie
0x18006e3c0  lea     r11, [rsp+78h+var_28]
0x18006e3c5  mov     rbx, [r11+38h]
0x18006e3c9  mov     rbp, [r11+40h]
0x18006e3cd  mov     rsp, r11
0x18006e3d0  pop     r15
0x18006e3d2  pop     r14
0x18006e3d4  pop     r13
0x18006e3d6  pop     rdi
0x18006e3d7  pop     rsi
0x18006e3d8  retn
```
