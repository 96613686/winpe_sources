# NDXGI::CDevice::CDevice(NDXGI::CDevice::TConstructorArgs const &)

- ea: `0x180045854`
- end: `0x180045f0c`
- name: `??0CDevice@NDXGI@@QEAA@AEBUTConstructorArgs@01@@Z`
- size: `1720`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, const struct NDXGI::CDevice::TConstructorArgs *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180045790`
- `0x1800a0d84`

## callees

- `0x180011080`
- `0x180027a98`
- `0x180045854`
- `0x180082470`
- `0x1800a0ef8`
- `0x1800aa9a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045971`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045997`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045a41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045c80`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045cca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045d0d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045d4e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045971`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045997`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045a41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045c80`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045cca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045d0d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045d4e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045935`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800459ba`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045a4f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045acc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045b3a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045ba8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045c0b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045935`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800459ba`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045a4f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045acc`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045b3a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045ba8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180045c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045ece`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045ece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ec0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ec0`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800458df`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800458df`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
NDXGI::CDevice *__fastcall NDXGI::CDevice::CDevice(
        NDXGI::CDevice *this,
        const struct NDXGI::CDevice::TConstructorArgs *a2)
{
  int v3; // ecx
  _QWORD *v4; // rax
  __int64 size_of; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _OWORD *v16; // rax
  __int64 (__fastcall **v17)(NDXGI::CDevice *, struct _D3DDDICB_ALLOCATE *); // rcx
  __int64 v18; // rdx
  HKEY hKey; // [rsp+88h] [rbp+50h] BYREF
  char *v21; // [rsp+90h] [rbp+58h]

  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = *((_QWORD *)a2 + 4);
  *((_QWORD *)this + 12) = qword_18022B838;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 224) = 0x10000;
  *((_DWORD *)this + 225) = *((_DWORD *)a2 + 13);
  *((_QWORD *)this + 116) = (char *)this + 928;
  *((_QWORD *)this + 117) = (char *)this + 928;
  *((_QWORD *)this + 118) = 1024;
  *((_QWORD *)this + 119) = operator new(0x400u);
  v3 = (unsigned int)QuirkIsEnabled(1048581) != 0 ? 1 : 3;
  *((_DWORD *)this + 240) = v3;
  *((_DWORD *)this + 241) = v3;
  *((_DWORD *)this + 242) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_QWORD *)this + 125) = 0;
  *((_DWORD *)this + 254) = -1;
  *(_QWORD *)((char *)this + 1020) = 0;
  InitializeSRWLock((PSRWLOCK)this + 129);
  *((_QWORD *)this + 130) = 0;
  *((_QWORD *)this + 131) = 0;
  v4 = operator new(0x88u);
  *v4 = v4;
  v4[1] = v4;
  *((_QWORD *)this + 130) = v4;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1056), 0xFA0u);
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 138) = 0;
  *((_QWORD *)this + 139) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 28, 0xFA0u);
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 147) = 0;
  InitializeSRWLock((PSRWLOCK)this + 148);
  *((_DWORD *)this + 298) = 0;
  *((_QWORD *)this + 150) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_QWORD *)this + 152) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_QWORD *)this + 155) = 0;
  *((_DWORD *)this + 312) = 0;
  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 158) = 0;
  size_of = std::_Get_size_of_n<24>(1);
  v6 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v6 = v6;
  v6[1] = v6;
  *((_QWORD *)this + 157) = v6;
  *((_QWORD *)this + 159) = 0;
  *((_QWORD *)this + 160) = 0;
  *((_QWORD *)this + 161) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1296), 0xFA0u);
  InitializeSRWLock((PSRWLOCK)this + 167);
  v21 = (char *)this + 1344;
  *((_DWORD *)this + 336) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 170) = 0;
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v7 = v7;
  v7[1] = v7;
  *((_QWORD *)this + 169) = v7;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_QWORD *)this + 173) = 0;
  *((_QWORD *)this + 174) = 7;
  *((_QWORD *)this + 175) = 8;
  *((_DWORD *)this + 336) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(
    (char *)this + 1368,
    16,
    *((_QWORD *)this + 169));
  *((_QWORD *)this + 176) = 0;
  InitializeSRWLock((PSRWLOCK)this + 177);
  v21 = (char *)this + 1424;
  *((_DWORD *)this + 356) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 180) = 0;
  v8 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v8 = v8;
  v8[1] = v8;
  *((_QWORD *)this + 179) = v8;
  *((_QWORD *)this + 181) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 184) = 7;
  *((_QWORD *)this + 185) = 8;
  *((_DWORD *)this + 356) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(
    (char *)this + 1448,
    16,
    *((_QWORD *)this + 179));
  *((_QWORD *)this + 186) = 0;
  InitializeSRWLock((PSRWLOCK)this + 187);
  v21 = (char *)this + 1504;
  *((_DWORD *)this + 376) = 0;
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  v9 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v9 = v9;
  v9[1] = v9;
  *((_QWORD *)this + 189) = v9;
  *((_QWORD *)this + 191) = 0;
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 7;
  *((_QWORD *)this + 195) = 8;
  *((_DWORD *)this + 376) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(
    (char *)this + 1528,
    16,
    *((_QWORD *)this + 189));
  *((_QWORD *)this + 196) = 0;
  InitializeSRWLock((PSRWLOCK)this + 197);
  v21 = (char *)this + 1584;
  *((_DWORD *)this + 396) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  v10 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v10 = v10;
  v10[1] = v10;
  *((_QWORD *)this + 199) = v10;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 7;
  *((_QWORD *)this + 205) = 8;
  *((_DWORD *)this + 396) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(
    (char *)this + 1608,
    16,
    *((_QWORD *)this + 199));
  InitializeSRWLock((PSRWLOCK)this + 206);
  v21 = (char *)this + 1656;
  *((_DWORD *)this + 414) = 0;
  *((_QWORD *)this + 208) = 0;
  *((_QWORD *)this + 209) = 0;
  v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v11 = v11;
  v11[1] = v11;
  *((_QWORD *)this + 208) = v11;
  *((_QWORD *)this + 210) = 0;
  *((_QWORD *)this + 211) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_QWORD *)this + 213) = 7;
  *((_QWORD *)this + 214) = 8;
  *((_DWORD *)this + 414) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(
    (char *)this + 1680,
    16,
    *((_QWORD *)this + 208));
  *((_QWORD *)this + 215) = 0;
  v21 = (char *)this + 1728;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1728), 0xFA0u);
  *((_QWORD *)this + 221) = 0;
  *((_QWORD *)this + 222) = 0;
  v12 = operator new(0x48u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  *((_QWORD *)this + 221) = v12;
  *((_QWORD *)this + 223) = 1;
  v21 = (char *)this + 1792;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1792), 0xFA0u);
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 0;
  v13 = operator new(0x38u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  *((_QWORD *)this + 229) = v13;
  *((_QWORD *)this + 231) = 1;
  v21 = (char *)this + 1856;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 1856), 0xFA0u);
  *((_QWORD *)this + 237) = 0;
  *((_QWORD *)this + 238) = 0;
  v14 = operator new(0x48u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *((_QWORD *)this + 237) = v14;
  *((_QWORD *)this + 239) = 1;
  v21 = (char *)this + 1920;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 48, 0xFA0u);
  *((_QWORD *)this + 245) = 0;
  *((_QWORD *)this + 246) = 0;
  v15 = operator new(0x30u);
  *v15 = v15;
  v15[1] = v15;
  v15[2] = v15;
  *((_WORD *)v15 + 12) = 257;
  *((_QWORD *)this + 245) = v15;
  *((_QWORD *)this + 247) = 1;
  *((_WORD *)this + 992) = 0;
  *((_BYTE *)this + 1986) = 0;
  *((_QWORD *)this + 249) = 0;
  *((_DWORD *)this + 500) = 0;
  *((_BYTE *)this + 2004) = 0;
  *((_QWORD *)this + 251) = 0;
  *((_QWORD *)this + 252) = 0;
  *((_QWORD *)this + 253) = 0;
  *((_QWORD *)this + 254) = 0;
  *((_QWORD *)this + 255) = 0;
  *((_WORD *)this + 1024) = 512;
  *(_QWORD *)((char *)this + 2052) = 0;
  *((_DWORD *)this + 515) = 0;
  v16 = (_OWORD *)((char *)this + 112);
  v17 = `NDXGI::CDevice::CDevice'::`2'::UMDDeviceKTCallbacks;
  v18 = 4;
  do
  {
    *v16 = *(_OWORD *)v17;
    v16[1] = *((_OWORD *)v17 + 1);
    v16[2] = *((_OWORD *)v17 + 2);
    v16[3] = *((_OWORD *)v17 + 3);
    v16[4] = *((_OWORD *)v17 + 4);
    v16[5] = *((_OWORD *)v17 + 5);
    v16[6] = *((_OWORD *)v17 + 6);
    v16[7] = *((_OWORD *)v17 + 7);
    v16 += 8;
    v17 += 16;
    --v18;
  }
  while ( v18 );
  *v16 = *(_OWORD *)v17;
  v16[1] = *((_OWORD *)v17 + 1);
  v16[2] = *((_OWORD *)v17 + 2);
  *(_OWORD *)((char *)this + 856) = *(_OWORD *)`NDXGI::CDevice::CDevice'::`2'::DXGICallbacks;
  *(_OWORD *)((char *)this + 872) = *(_OWORD *)off_1801DFF70;
  *((_QWORD *)this + 111) = NDXGI::CDevice::SubmitPresentToHwQueueCB;
  *(_OWORD *)((char *)this + 904) = 0;
  *((_QWORD *)this + 115) = 0;
  *((_DWORD *)this + 228) = 8;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\GraphicsDrivers", 0, 0x20019u, &hKey) )
    RegCloseKey(hKey);
  memset_0((char *)this + 680, 0, 0xB0u);
  *((_QWORD *)this + 126) = 0;
  qword_18022B838 = 0;
  return this;
}

```

## disassembly

```asm
0x180045854  mov     [rsp-40h+arg_0], rcx
0x180045859  push    rbp
0x18004585a  push    rbx
0x18004585b  push    rsi
0x18004585c  push    rdi
0x18004585d  push    r12
0x18004585f  push    r13
0x180045861  push    r14
0x180045863  push    r15
0x180045865  mov     rbp, rsp
0x180045868  sub     rsp, 38h
0x18004586c  mov     rsi, rcx
0x18004586f  xor     edi, edi
0x180045871  mov     [rcx+30h], edi
0x180045874  mov     [rcx+38h], rdi
0x180045878  mov     [rcx+40h], rdi
0x18004587c  mov     [rcx+48h], rdi
0x180045880  mov     [rcx+50h], rdi
0x180045884  mov     rax, [rdx+20h]
0x180045888  mov     [rcx+58h], rax
0x18004588c  mov     rax, cs:qword_18022B838
0x180045893  mov     [rcx+60h], rax
0x180045897  mov     [rcx+68h], edi
0x18004589a  mov     [rcx+2A0h], rdi
0x1800458a1  mov     dword ptr [rcx+380h], 10000h
0x1800458ab  mov     eax, [rdx+34h]
0x1800458ae  mov     [rcx+384h], eax
0x1800458b4  lea     rax, [rcx+3A0h]
0x1800458bb  mov     [rax], rax
0x1800458be  mov     [rax+8], rax
0x1800458c2  mov     ecx, 400h; dwBytes
0x1800458c7  mov     [rsi+3B0h], rcx
0x1800458ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800458d3  mov     [rsi+3B8h], rax
0x1800458da  mov     ecx, 100005h
0x1800458df  call    cs:__imp_QuirkIsEnabled
0x1800458e5  neg     eax
0x1800458e7  sbb     ecx, ecx
0x1800458e9  and     ecx, 0FFFFFFFEh
0x1800458ec  add     ecx, 3
0x1800458ef  mov     [rsi+3C0h], ecx
0x1800458f5  mov     [rsi+3C4h], ecx
0x1800458fb  mov     [rsi+3C8h], edi
0x180045901  mov     [rsi+3D0h], rdi
0x180045908  mov     [rsi+3D8h], rdi
0x18004590f  mov     [rsi+3E0h], rdi
0x180045916  mov     [rsi+3E8h], rdi
0x18004591d  mov     dword ptr [rsi+3F8h], 0FFFFFFFFh
0x180045927  mov     [rsi+3FCh], rdi
0x18004592e  lea     rcx, [rsi+408h]; SRWLock
0x180045935  call    cs:__imp_InitializeSRWLock
0x18004593b  mov     [rsi+410h], rdi
0x180045942  mov     [rsi+418h], rdi
0x180045949  mov     ecx, 88h; dwBytes
0x18004594e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045953  mov     [rax], rax
0x180045956  mov     [rax+8], rax
0x18004595a  mov     [rsi+410h], rax
0x180045961  lea     rcx, [rsi+420h]; lpCriticalSection
0x180045968  mov     r13d, 0FA0h
0x18004596e  mov     edx, r13d; dwSpinCount
0x180045971  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045977  nop
0x180045978  mov     [rsi+448h], rdi
0x18004597f  mov     [rsi+450h], rdi
0x180045986  mov     [rsi+458h], rdi
0x18004598d  lea     rcx, [rsi+460h]; lpCriticalSection
0x180045994  mov     edx, r13d; dwSpinCount
0x180045997  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004599d  nop
0x18004599e  mov     [rsi+488h], rdi
0x1800459a5  mov     [rsi+490h], rdi
0x1800459ac  mov     [rsi+498h], rdi
0x1800459b3  lea     rcx, [rsi+4A0h]; SRWLock
0x1800459ba  call    cs:__imp_InitializeSRWLock
0x1800459c0  mov     [rsi+4A8h], edi
0x1800459c6  mov     [rsi+4B0h], rdi
0x1800459cd  mov     [rsi+4B8h], rdi
0x1800459d4  mov     [rsi+4C0h], rdi
0x1800459db  mov     [rsi+4C8h], rdi
0x1800459e2  mov     [rsi+4D0h], rdi
0x1800459e9  mov     [rsi+4D8h], rdi
0x1800459f0  mov     [rsi+4E0h], edi
0x1800459f6  mov     [rsi+4E8h], rdi
0x1800459fd  mov     [rsi+4F0h], rdi
0x180045a04  lea     ecx, [rdi+1]
0x180045a07  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x180045a0c  mov     rcx, rax
0x180045a0f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045a14  mov     [rax], rax
0x180045a17  mov     [rax+8], rax
0x180045a1b  mov     [rsi+4E8h], rax
0x180045a22  mov     [rsi+4F8h], rdi
0x180045a29  mov     [rsi+500h], rdi
0x180045a30  mov     [rsi+508h], rdi
0x180045a37  lea     rcx, [rsi+510h]; lpCriticalSection
0x180045a3e  mov     edx, r13d; dwSpinCount
0x180045a41  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045a47  nop
0x180045a48  lea     rcx, [rsi+538h]; SRWLock
0x180045a4f  call    cs:__imp_InitializeSRWLock
0x180045a55  lea     rbx, [rsi+540h]
0x180045a5c  mov     [rbp+arg_10], rbx
0x180045a60  mov     [rbx], edi
0x180045a62  mov     [rbx+8], rdi
0x180045a66  mov     [rbx+10h], rdi
0x180045a6a  lea     r12d, [rdi+20h]
0x180045a6e  mov     ecx, r12d
0x180045a71  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045a76  mov     [rax], rax
0x180045a79  mov     [rax+8], rax
0x180045a7d  mov     [rbx+8], rax
0x180045a81  lea     rcx, [rbx+18h]
0x180045a85  mov     [rcx], rdi
0x180045a88  mov     [rcx+8], rdi
0x180045a8c  mov     [rcx+10h], rdi
0x180045a90  lea     r15d, [rdi+7]
0x180045a94  mov     [rbx+30h], r15
0x180045a98  mov     qword ptr [rbx+38h], 8
0x180045aa0  mov     r14d, 3F800000h
0x180045aa6  mov     [rbx], r14d
0x180045aa9  mov     r8, [rbx+8]
0x180045aad  lea     edi, [r12-10h]
0x180045ab2  mov     edx, edi
0x180045ab4  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>)
0x180045ab9  nop
0x180045aba  mov     qword ptr [rsi+580h], 0
0x180045ac5  lea     rcx, [rsi+588h]; SRWLock
0x180045acc  call    cs:__imp_InitializeSRWLock
0x180045ad2  lea     rbx, [rsi+590h]
0x180045ad9  mov     [rbp+arg_10], rbx
0x180045add  xor     eax, eax
0x180045adf  mov     [rbx], eax
0x180045ae1  mov     [rbx+8], rax
0x180045ae5  mov     [rbx+10h], rax
0x180045ae9  mov     ecx, r12d
0x180045aec  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045af1  mov     [rax], rax
0x180045af4  mov     [rax+8], rax
0x180045af8  mov     [rbx+8], rax
0x180045afc  lea     rcx, [rbx+18h]
0x180045b00  xor     eax, eax
0x180045b02  mov     [rcx], rax
0x180045b05  mov     [rcx+8], rax
0x180045b09  mov     [rcx+10h], rax
0x180045b0d  mov     [rbx+30h], r15
0x180045b11  mov     qword ptr [rbx+38h], 8
0x180045b19  mov     [rbx], r14d
0x180045b1c  mov     r8, [rbx+8]
0x180045b20  mov     edx, edi
0x180045b22  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>)
0x180045b27  nop
0x180045b28  mov     qword ptr [rsi+5D0h], 0
0x180045b33  lea     rcx, [rsi+5D8h]; SRWLock
0x180045b3a  call    cs:__imp_InitializeSRWLock
0x180045b40  lea     rbx, [rsi+5E0h]
0x180045b47  mov     [rbp+arg_10], rbx
0x180045b4b  xor     eax, eax
0x180045b4d  mov     [rbx], eax
0x180045b4f  mov     [rbx+8], rax
0x180045b53  mov     [rbx+10h], rax
0x180045b57  mov     ecx, r12d
0x180045b5a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045b5f  mov     [rax], rax
0x180045b62  mov     [rax+8], rax
0x180045b66  mov     [rbx+8], rax
0x180045b6a  lea     rcx, [rbx+18h]
0x180045b6e  xor     eax, eax
0x180045b70  mov     [rcx], rax
0x180045b73  mov     [rcx+8], rax
0x180045b77  mov     [rcx+10h], rax
0x180045b7b  mov     [rbx+30h], r15
0x180045b7f  mov     qword ptr [rbx+38h], 8
0x180045b87  mov     [rbx], r14d
0x180045b8a  mov     r8, [rbx+8]
0x180045b8e  mov     edx, edi
0x180045b90  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>)
0x180045b95  nop
0x180045b96  mov     qword ptr [rsi+620h], 0
0x180045ba1  lea     rcx, [rsi+628h]; SRWLock
0x180045ba8  call    cs:__imp_InitializeSRWLock
0x180045bae  lea     rbx, [rsi+630h]
0x180045bb5  mov     [rbp+arg_10], rbx
0x180045bb9  xor     eax, eax
0x180045bbb  mov     [rbx], eax
0x180045bbd  mov     [rbx+8], rax
0x180045bc1  mov     [rbx+10h], rax
0x180045bc5  mov     ecx, r12d
0x180045bc8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045bcd  mov     [rax], rax
0x180045bd0  mov     [rax+8], rax
0x180045bd4  mov     [rbx+8], rax
0x180045bd8  lea     rcx, [rbx+18h]
0x180045bdc  xor     eax, eax
0x180045bde  mov     [rcx], rax
0x180045be1  mov     [rcx+8], rax
0x180045be5  mov     [rcx+10h], rax
0x180045be9  mov     [rbx+30h], r15
0x180045bed  mov     qword ptr [rbx+38h], 8
0x180045bf5  mov     [rbx], r14d
0x180045bf8  mov     r8, [rbx+8]
0x180045bfc  mov     edx, edi
0x180045bfe  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>)
0x180045c03  nop
0x180045c04  lea     rcx, [rsi+670h]; SRWLock
0x180045c0b  call    cs:__imp_InitializeSRWLock
0x180045c11  lea     rbx, [rsi+678h]
0x180045c18  mov     [rbp+arg_10], rbx
0x180045c1c  xor     eax, eax
0x180045c1e  mov     [rbx], eax
0x180045c20  mov     [rbx+8], rax
0x180045c24  mov     [rbx+10h], rax
0x180045c28  mov     ecx, r12d
0x180045c2b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180045c30  mov     [rax], rax
0x180045c33  mov     [rax+8], rax
0x180045c37  mov     [rbx+8], rax
0x180045c3b  lea     rcx, [rbx+18h]
0x180045c3f  xor     r12d, r12d
0x180045c42  mov     [rcx], r12
0x180045c45  mov     [rcx+8], r12
0x180045c49  mov     [rcx+10h], r12
0x180045c4d  mov     [rbx+30h], r15
0x180045c51  mov     qword ptr [rbx+38h], 8
0x180045c59  mov     [rbx], r14d
0x180045c5c  mov     r8, [rbx+8]
0x180045c60  mov     edx, edi
0x180045c62  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>>>)
0x180045c67  nop
0x180045c68  mov     [rsi+6B8h], r12
0x180045c6f  lea     rdi, [rsi+6C0h]
0x180045c76  mov     [rbp+arg_10], rdi
0x180045c7a  mov     edx, r13d; dwSpinCount
0x180045c7d  mov     rcx, rdi; lpCriticalSection
0x180045c80  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045c86  nop
0x180045c87  mov     [rdi+28h], r12
0x180045c8b  mov     [rdi+30h], r12
0x180045c8f  lea     r14d, [r15+41h]
0x180045c93  mov     ecx, r14d; dwBytes
0x180045c96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045c9b  mov     [rax], rax
0x180045c9e  mov     [rax+8], rax
0x180045ca2  mov     [rax+10h], rax
0x180045ca6  lea     r15d, [r12+1]
0x180045cab  mov     word ptr [rax+18h], 101h
0x180045cb1  mov     [rdi+28h], rax
0x180045cb5  mov     [rdi+38h], r15
0x180045cb9  lea     rdi, [rsi+700h]
0x180045cc0  mov     [rbp+arg_10], rdi
0x180045cc4  mov     edx, r13d; dwSpinCount
0x180045cc7  mov     rcx, rdi; lpCriticalSection
0x180045cca  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045cd0  nop
0x180045cd1  mov     [rdi+28h], r12
0x180045cd5  mov     [rdi+30h], r12
0x180045cd9  lea     ecx, [r12+38h]; dwBytes
0x180045cde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045ce3  mov     [rax], rax
0x180045ce6  mov     [rax+8], rax
0x180045cea  mov     [rax+10h], rax
0x180045cee  mov     word ptr [rax+18h], 101h
0x180045cf4  mov     [rdi+28h], rax
0x180045cf8  mov     [rdi+38h], r15
0x180045cfc  lea     rdi, [rsi+740h]
0x180045d03  mov     [rbp+arg_10], rdi
0x180045d07  mov     edx, r13d; dwSpinCount
0x180045d0a  mov     rcx, rdi; lpCriticalSection
0x180045d0d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045d13  nop
0x180045d14  mov     [rdi+28h], r12
0x180045d18  mov     [rdi+30h], r12
0x180045d1c  mov     ecx, r14d; dwBytes
0x180045d1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045d24  mov     [rax], rax
0x180045d27  mov     [rax+8], rax
0x180045d2b  mov     [rax+10h], rax
0x180045d2f  mov     word ptr [rax+18h], 101h
0x180045d35  mov     [rdi+28h], rax
0x180045d39  mov     [rdi+38h], r15
0x180045d3d  lea     rdi, [rsi+780h]
0x180045d44  mov     [rbp+arg_10], rdi
0x180045d48  mov     edx, r13d; dwSpinCount
0x180045d4b  mov     rcx, rdi; lpCriticalSection
0x180045d4e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045d54  nop
0x180045d55  mov     [rdi+28h], r12
0x180045d59  mov     [rdi+30h], r12
0x180045d5d  lea     ecx, [r12+30h]; dwBytes
0x180045d62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045d67  mov     [rax], rax
0x180045d6a  mov     [rax+8], rax
0x180045d6e  mov     [rax+10h], rax
0x180045d72  mov     word ptr [rax+18h], 101h
0x180045d78  mov     [rdi+28h], rax
0x180045d7c  mov     [rdi+38h], r15
0x180045d80  mov     [rsi+7C0h], r12w
0x180045d88  mov     [rsi+7C2h], r12b
0x180045d8f  mov     [rsi+7C8h], r12
0x180045d96  mov     [rsi+7D0h], r12d
  ... truncated ...
```
