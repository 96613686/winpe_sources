# CExtensionHandler::ReadExtensionsFromRegistry(HKEY__ *)

- ea: `0x1800145f8`
- end: `0x1800148ad`
- name: `?ReadExtensionsFromRegistry@CExtensionHandler@@IEAAJPEAUHKEY__@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CExtensionHandler *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800143f0`

## callees

- `0x180002034`
- `0x180013280`
- `0x180013320`
- `0x180013c98`
- `0x1800145f8`
- `0x180014b20`
- `0x18001504c`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014728`
- `msvcrt!_wcsicmp` at `0x180014728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014837`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014837`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800146b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800146b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014669`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014669`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014711`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014711`

## pseudocode

```c
__int64 __fastcall CExtensionHandler::ReadExtensionsFromRegistry(CExtensionHandler *this, HKEY a2)
{
  HKEY v3; // r14
  LSTATUS v4; // eax
  int inited; // ebx
  bool v6; // cc
  DWORD v7; // edi
  CMvExtensionKey *v8; // rax
  CMvExtensionKey *v9; // rdx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rdi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  CMvExtensionKey *v16[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  cSubKeys = 0;
  cchName = 0;
  *(_OWORD *)v16 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\OEM\\ADC\\CustomizationKeys", 0, 0x20019u, &hKey) )
    goto LABEL_21;
  v3 = hKey;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  inited = v4;
  v6 = v4 <= 0;
  if ( !v4 )
  {
    if ( cSubKeys )
    {
      v7 = 0;
      while ( 1 )
      {
        cchName = 260;
        v4 = RegEnumKeyExW(v3, v7, Name, &cchName, 0, 0, 0, 0);
        inited = v4;
        v6 = v4 <= 0;
        if ( v4 )
          goto LABEL_3;
        if ( _wcsicmp(Name, L"CarrierID") || *((_DWORD *)this + 15) )
        {
          v8 = (CMvExtensionKey *)operator new(0x278u);
          v9 = v8;
          if ( v8 )
          {
            *((_DWORD *)v8 + 131) = 0;
            *((_DWORD *)v8 + 150) = 0;
            *((_QWORD *)v8 + 76) = 0;
            *((_DWORD *)v8 + 154) = 0;
            *((_QWORD *)v8 + 78) = 0;
            *(_WORD *)v8 = 0;
          }
          else
          {
            v9 = 0;
          }
          v17 = 0;
          std::shared_ptr<CMvExtensionKey>::_Resetp<CMvExtensionKey>((CMvExtensionKey **)&v17, v9);
          std::shared_ptr<CMvExtensionKey>::operator=(v16, (__int64 *)&v17);
          v10 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
          if ( *((_QWORD *)&v17 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
              if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
            }
          }
          inited = CMvExtensionKey::InitExtensionKey((HKEY *)v16[0], v3, Name);
          if ( inited < 0 )
            goto LABEL_22;
          std::vector<std::shared_ptr<CMvExtensionKey>>::push_back((__int64 *)this + 4, (__int64 *)v16);
        }
        if ( ++v7 >= cSubKeys )
        {
          ____Sort_PEAV__shared_ptr_VCMvExtensionKey___std___JP6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0_0_JP6AHV__shared_ptr___CBVCMvExtensionKey___0_2__E_Z(
            *((__int64 **)this + 4),
            *((__int64 **)this + 5),
            (__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 4);
          break;
        }
      }
    }
LABEL_21:
    inited = 0;
    goto LABEL_22;
  }
LABEL_3:
  if ( !v6 )
    inited = (unsigned __int16)v4 | 0x80070000;
LABEL_22:
  *((_DWORD *)this + 14) = 1;
  if ( hKey )
    RegCloseKey(hKey);
  v11 = (volatile signed __int32 *)v16[1];
  if ( v16[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800145f8  mov     [rsp-8+arg_8], rbx
0x1800145fd  mov     [rsp-8+arg_10], rsi
0x180014602  push    rbp
0x180014603  push    rdi
0x180014604  push    r12
0x180014606  push    r14
0x180014608  push    r15
0x18001460a  lea     rbp, [rsp-1B0h]
0x180014612  sub     rsp, 2B0h
0x180014619  mov     rax, cs:__security_cookie
0x180014620  xor     rax, rsp
0x180014623  mov     [rbp+1D0h+var_30], rax
0x18001462a  mov     rsi, rcx
0x18001462d  xor     r15d, r15d
0x180014630  mov     [rsp+2D0h+cSubKeys], r15d
0x180014635  mov     [rsp+2D0h+cchName], r15d
0x18001463a  xorps   xmm0, xmm0
0x18001463d  movdqu  xmmword ptr [rsp+2D0h+var_260], xmm0
0x180014643  mov     [rsp+2D0h+hKey], r15
0x180014648  lea     rax, [rsp+2D0h+hKey]
0x18001464d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180014652  mov     r9d, 20019h; samDesired
0x180014658  xor     r8d, r8d; ulOptions
0x18001465b  lea     rdx, ?gc_szCustomizationRootReg@@3QBGB; "Software\\OEM\\ADC\\CustomizationKeys"
0x180014662  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014669  call    cs:__imp_RegOpenKeyExW
0x18001466f  or      r12d, 0FFFFFFFFh
0x180014673  test    eax, eax
0x180014675  jnz     loc_180014823
0x18001467b  mov     r14, [rsp+2D0h+hKey]
0x180014680  mov     [rsp+2D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180014685  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001468a  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001468f  mov     [rsp+2D0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180014694  mov     [rsp+2D0h+lpcValues], r15; lpcValues
0x180014699  mov     [rsp+2D0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001469e  mov     [rsp+2D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800146a3  lea     rax, [rsp+2D0h+cSubKeys]
0x1800146a8  mov     [rsp+2D0h+phkResult], rax; lpcSubKeys
0x1800146ad  xor     r9d, r9d; lpReserved
0x1800146b0  xor     r8d, r8d; lpcchClass
0x1800146b3  xor     edx, edx; lpClass
0x1800146b5  mov     rcx, r14; hKey
0x1800146b8  call    cs:__imp_RegQueryInfoKeyW
0x1800146be  mov     ebx, eax
0x1800146c0  test    eax, eax
0x1800146c2  jz      short loc_1800146D8
0x1800146c4  jle     loc_180014826
0x1800146ca  movzx   ebx, ax
0x1800146cd  or      ebx, 80070000h
0x1800146d3  jmp     loc_180014826
0x1800146d8  mov     eax, [rsp+2D0h+cSubKeys]
0x1800146dc  test    eax, eax
0x1800146de  jz      loc_180014823
0x1800146e4  mov     edi, r15d
0x1800146e7  mov     [rsp+2D0h+cchName], 104h
0x1800146ef  mov     [rsp+2D0h+lpcValues], r15; lpftLastWriteTime
0x1800146f4  mov     [rsp+2D0h+lpcbMaxClassLen], r15; lpcchClass
0x1800146f9  mov     [rsp+2D0h+lpcbMaxSubKeyLen], r15; lpClass
0x1800146fe  mov     [rsp+2D0h+phkResult], r15; lpReserved
0x180014703  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180014708  lea     r8, [rbp+1D0h+Name]; lpName
0x18001470c  mov     edx, edi; dwIndex
0x18001470e  mov     rcx, r14; hKey
0x180014711  call    cs:__imp_RegEnumKeyExW
0x180014717  mov     ebx, eax
0x180014719  test    eax, eax
0x18001471b  jnz     short loc_1800146C4
0x18001471d  lea     rdx, ?gc_wszCarrierID@@3QBGB; "CarrierID"
0x180014724  lea     rcx, [rbp+1D0h+Name]; String1
0x180014728  call    cs:__imp__wcsicmp
0x18001472e  test    eax, eax
0x180014730  jnz     short loc_18001473C
0x180014732  cmp     [rsi+3Ch], r15d
0x180014736  jz      loc_180014800
0x18001473c  mov     ecx, 278h; Size
0x180014741  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014746  mov     rdx, rax
0x180014749  test    rax, rax
0x18001474c  jz      short loc_180014777
0x18001474e  mov     [rax+20Ch], r15d
0x180014755  mov     [rax+258h], r15d
0x18001475c  mov     [rax+260h], r15
0x180014763  mov     [rax+268h], r15d
0x18001476a  mov     [rax+270h], r15
0x180014771  mov     [rax], r15w
0x180014775  jmp     short loc_18001477A
0x180014777  mov     rdx, r15
0x18001477a  xorps   xmm0, xmm0
0x18001477d  movdqu  [rbp+1D0h+var_250], xmm0
0x180014782  lea     rcx, [rbp+1D0h+var_250]
0x180014786  call    ??$_Resetp@VCMvExtensionKey@@@?$shared_ptr@VCMvExtensionKey@@@std@@AEAAXPEAVCMvExtensionKey@@@Z; std::shared_ptr<CMvExtensionKey>::_Resetp<CMvExtensionKey>(CMvExtensionKey *)
0x18001478b  lea     rdx, [rbp+1D0h+var_250]
0x18001478f  lea     rcx, [rsp+2D0h+var_260]
0x180014794  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x180014799  nop
0x18001479a  mov     rbx, qword ptr [rbp+1D0h+var_250+8]
0x18001479e  test    rbx, rbx
0x1800147a1  jz      short loc_1800147DB
0x1800147a3  mov     eax, r12d
0x1800147a6  lock xadd [rbx+8], eax
0x1800147ab  add     eax, r12d
0x1800147ae  jnz     short loc_1800147DB
0x1800147b0  mov     rax, [rbx]
0x1800147b3  mov     rcx, rbx
0x1800147b6  mov     rax, [rax]
0x1800147b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147be  mov     eax, r12d
0x1800147c1  lock xadd [rbx+0Ch], eax
0x1800147c6  add     eax, r12d
0x1800147c9  jnz     short loc_1800147DB
0x1800147cb  mov     rax, [rbx]
0x1800147ce  mov     rcx, rbx
0x1800147d1  mov     rax, [rax+8]
0x1800147d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147da  nop
0x1800147db  lea     r8, [rbp+1D0h+Name]; unsigned __int16 *
0x1800147df  mov     rdx, r14; hKey
0x1800147e2  mov     rcx, [rsp+2D0h+var_260]; this
0x1800147e7  call    ?InitExtensionKey@CMvExtensionKey@@QEAAJPEAUHKEY__@@PEBG@Z; CMvExtensionKey::InitExtensionKey(HKEY__ *,ushort const *)
0x1800147ec  mov     ebx, eax
0x1800147ee  test    eax, eax
0x1800147f0  js      short loc_180014826
0x1800147f2  lea     rcx, [rsi+20h]
0x1800147f6  lea     rdx, [rsp+2D0h+var_260]
0x1800147fb  call    ?push_back@?$vector@V?$shared_ptr@VCMvExtensionKey@@@std@@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VCMvExtensionKey@@@2@@Z; std::vector<std::shared_ptr<CMvExtensionKey>>::push_back(std::shared_ptr<CMvExtensionKey> const &)
0x180014800  inc     edi
0x180014802  cmp     edi, [rsp+2D0h+cSubKeys]
0x180014806  jb      loc_1800146E7
0x18001480c  mov     rdx, [rsi+28h]
0x180014810  mov     rcx, [rsi+20h]
0x180014814  mov     r8, rdx
0x180014817  sub     r8, rcx
0x18001481a  sar     r8, 4
0x18001481e  call    ??$_Sort@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@0_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@2@_E@Z
0x180014823  mov     ebx, r15d
0x180014826  mov     dword ptr [rsi+38h], 1
0x18001482d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180014832  test    rcx, rcx
0x180014835  jz      short loc_18001483E
0x180014837  call    cs:__imp_RegCloseKey
0x18001483d  nop
0x18001483e  mov     rdi, [rsp+2D0h+var_260+8]
0x180014843  test    rdi, rdi
0x180014846  jz      short loc_180014880
0x180014848  mov     eax, r12d
0x18001484b  lock xadd [rdi+8], eax
0x180014850  add     eax, r12d
0x180014853  jnz     short loc_180014880
0x180014855  mov     rax, [rdi]
0x180014858  mov     rcx, rdi
0x18001485b  mov     rax, [rax]
0x18001485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014863  mov     eax, r12d
0x180014866  lock xadd [rdi+0Ch], eax
0x18001486b  add     eax, r12d
0x18001486e  jnz     short loc_180014880
0x180014870  mov     rax, [rdi]
0x180014873  mov     rcx, rdi
0x180014876  mov     rax, [rax+8]
0x18001487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001487f  nop
0x180014880  mov     eax, ebx
0x180014882  mov     rcx, [rbp+1D0h+var_30]
0x180014889  xor     rcx, rsp; StackCookie
0x18001488c  call    __security_check_cookie
0x180014891  lea     r11, [rsp+2D0h+var_20]
0x180014899  mov     rbx, [r11+38h]
0x18001489d  mov     rsi, [r11+40h]
0x1800148a1  mov     rsp, r11
0x1800148a4  pop     r15
0x1800148a6  pop     r14
0x1800148a8  pop     r12
0x1800148aa  pop     rdi
0x1800148ab  pop     rbp
0x1800148ac  retn
```
