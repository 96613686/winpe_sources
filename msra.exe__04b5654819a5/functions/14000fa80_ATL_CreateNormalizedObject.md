# ATL::CreateNormalizedObject

- ea: `0x14000fa80`
- end: `0x14000fcae`
- name: `ATL::CreateNormalizedObject`
- size: `558`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpsz@<rcx>, BSTR pbstr)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000f180`

## callees

- `0x14000fa80`
- `0x1400104d0`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x14000fbb4`
- `ole32!CLSIDFromString` at `0x14000fbb4`
- `ole32!CLSIDFromProgID` at `0x14000fbc2`
- `ole32!CLSIDFromProgID` at `0x14000fbc2`
- `ole32!CoGetClassObject` at `0x14000fc0d`
- `ole32!CoGetClassObject` at `0x14000fc0d`
- `ole32!CoCreateInstance` at `0x14000fb56`
- `ole32!CoCreateInstance` at `0x14000fc78`
- `ole32!CoCreateInstance` at `0x14000fb56`
- `ole32!CoCreateInstance` at `0x14000fc78`
- `OLEAUT32!__imp_SysStringLen` at `0x14000fbdb`
- `OLEAUT32!__imp_SysStringLen` at `0x14000fbdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CreateNormalizedObject(LPCWSTR lpsz, __int64 a2, LPVOID *a3, _BYTE *a4, BSTR pbstr)
{
  GUID *v9; // rcx
  unsigned int Instance; // eax
  unsigned int ClassObject; // edi
  __int64 v12; // rax
  HRESULT v13; // eax
  LPVOID v14; // [rsp+40h] [rbp-48h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-40h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pclsid = 0;
  *a4 = 0;
  if ( lpsz && *lpsz )
  {
    if ( ((*lpsz - 77) & 0xFFDF) != 0
      || ((lpsz[1] - 83) & 0xFFDF) != 0
      || ((lpsz[2] - 72) & 0xFFDF) != 0
      || ((lpsz[3] - 84) & 0xFFDF) != 0
      || ((lpsz[4] - 77) & 0xFFDF) != 0
      || ((lpsz[5] - 76) & 0xFFDF) != 0
      || lpsz[6] != 58 )
    {
      if ( !ATL::CAtlModule::FindOneOf(lpsz, L":") )
      {
        ClassObject = -2147467259;
        v12 = -1;
        do
          ++v12;
        while ( lpsz[v12] );
        if ( (int)v12 >= 255 )
          return ClassObject;
        v13 = *lpsz == 123 ? CLSIDFromString(lpsz, &pclsid) : CLSIDFromProgID(lpsz, &pclsid);
        ClassObject = v13;
        if ( v13 < 0 )
          return ClassObject;
        if ( SysStringLen(pbstr) )
        {
          v14 = 0;
          ClassObject = CoGetClassObject(&pclsid, 1u, 0, &GUID_b196b28f_bab4_101a_b69c_00aa00341d07, &v14);
          if ( (ClassObject & 0x80000000) == 0 )
            ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *, BSTR, LPVOID *))(*(_QWORD *)v14 + 56LL))(
                            v14,
                            0,
                            0,
                            &GUID_00000000_0000_0000_c000_000000000046,
                            pbstr,
                            a3);
          if ( v14 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
          return ClassObject;
        }
        return (unsigned int)CoCreateInstance(&pclsid, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
      }
      v9 = &GUID_8856f961_340a_11d0_a96b_00c04fd705a2;
    }
    else
    {
      v9 = &GUID_25336920_03f9_11cf_8fd0_00aa00686f13;
    }
    Instance = CoCreateInstance(v9, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
    *a4 = 1;
    return Instance;
  }
  return 0;
}

```

## disassembly

```asm
0x14000fa80  mov     [rsp+arg_8], rbx
0x14000fa85  push    rbp
0x14000fa86  push    rsi
0x14000fa87  push    rdi
0x14000fa88  push    r14
0x14000fa8a  push    r15
0x14000fa8c  sub     rsp, 60h
0x14000fa90  mov     rax, cs:__security_cookie
0x14000fa97  xor     rax, rsp
0x14000fa9a  mov     [rsp+88h+var_30], rax
0x14000fa9f  mov     r14, r9
0x14000faa2  mov     rsi, r8
0x14000faa5  mov     rbx, rcx
0x14000faa8  mov     rbp, [rsp+88h+pbstr]
0x14000fab0  xor     r15d, r15d
0x14000fab3  test    r8, r8
0x14000fab6  jnz     short loc_14000FAC2
0x14000fab8  mov     eax, 80004003h
0x14000fabd  jmp     loc_14000FC8C
0x14000fac2  mov     [r8], r15
0x14000fac5  xorps   xmm0, xmm0
0x14000fac8  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x14000facd  mov     [r9], r15b
0x14000fad0  test    rbx, rbx
0x14000fad3  jz      loc_14000FC8A
0x14000fad9  movzx   eax, word ptr [rcx]
0x14000fadc  test    ax, ax
0x14000fadf  jz      loc_14000FC8A
0x14000fae5  sub     ax, 4Dh ; 'M'
0x14000fae9  mov     ecx, 0FFDFh
0x14000faee  test    cx, ax
0x14000faf1  jnz     short loc_14000FB6B
0x14000faf3  movzx   eax, word ptr [rbx+2]
0x14000faf7  sub     ax, 53h ; 'S'
0x14000fafb  test    cx, ax
0x14000fafe  jnz     short loc_14000FB6B
0x14000fb00  movzx   eax, word ptr [rbx+4]
0x14000fb04  sub     ax, 48h ; 'H'
0x14000fb08  test    cx, ax
0x14000fb0b  jnz     short loc_14000FB6B
0x14000fb0d  movzx   eax, word ptr [rbx+6]
0x14000fb11  sub     ax, 54h ; 'T'
0x14000fb15  test    cx, ax
0x14000fb18  jnz     short loc_14000FB6B
0x14000fb1a  movzx   eax, word ptr [rbx+8]
0x14000fb1e  sub     ax, 4Dh ; 'M'
0x14000fb22  test    cx, ax
0x14000fb25  jnz     short loc_14000FB6B
0x14000fb27  movzx   eax, word ptr [rbx+0Ah]
0x14000fb2b  sub     ax, 4Ch ; 'L'
0x14000fb2f  test    cx, ax
0x14000fb32  jnz     short loc_14000FB6B
0x14000fb34  cmp     word ptr [rbx+0Ch], 3Ah ; ':'
0x14000fb39  jnz     short loc_14000FB6B
0x14000fb3b  lea     rcx, _GUID_25336920_03f9_11cf_8fd0_00aa00686f13; rclsid
0x14000fb42  mov     r8d, 1; dwClsContext
0x14000fb48  xor     edx, edx; pUnkOuter
0x14000fb4a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14000fb51  mov     [rsp+88h+ppv], rsi; ppv
0x14000fb56  call    cs:__imp_CoCreateInstance
0x14000fb5d  nop     dword ptr [rax+rax+00h]
0x14000fb62  mov     byte ptr [r14], 1
0x14000fb66  jmp     loc_14000FC84
0x14000fb6b  lea     rdx, asc_140053C98; ":"
0x14000fb72  mov     rcx, rbx; lpsz
0x14000fb75  call    ?FindOneOf@CAtlModule@ATL@@SAPEBGPEBG0@Z; ATL::CAtlModule::FindOneOf(ushort const *,ushort const *)
0x14000fb7a  test    rax, rax
0x14000fb7d  jz      short loc_14000FB88
0x14000fb7f  lea     rcx, _GUID_8856f961_340a_11d0_a96b_00c04fd705a2
0x14000fb86  jmp     short loc_14000FB42
0x14000fb88  mov     edi, 80004005h
0x14000fb8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000fb91  inc     rax
0x14000fb94  cmp     [rbx+rax*2], r15w
0x14000fb99  jnz     short loc_14000FB91
0x14000fb9b  cmp     eax, 0FFh
0x14000fba0  jge     loc_14000FC86
0x14000fba6  lea     rdx, [rsp+88h+pclsid]; lpclsid
0x14000fbab  mov     rcx, rbx; lpszProgID
0x14000fbae  cmp     word ptr [rbx], 7Bh ; '{'
0x14000fbb2  jnz     short loc_14000FBC2
0x14000fbb4  call    cs:__imp_CLSIDFromString
0x14000fbbb  nop     dword ptr [rax+rax+00h]
0x14000fbc0  jmp     short loc_14000FBCE
0x14000fbc2  call    cs:__imp_CLSIDFromProgID
0x14000fbc9  nop     dword ptr [rax+rax+00h]
0x14000fbce  mov     edi, eax
0x14000fbd0  test    eax, eax
0x14000fbd2  js      loc_14000FC86
0x14000fbd8  mov     rcx, rbp; pbstr
0x14000fbdb  call    cs:__imp_SysStringLen
0x14000fbe2  nop     dword ptr [rax+rax+00h]
0x14000fbe7  test    eax, eax
0x14000fbe9  jz      short loc_14000FC61
0x14000fbeb  mov     [rsp+88h+var_48], r15
0x14000fbf0  lea     rax, [rsp+88h+var_48]
0x14000fbf5  mov     [rsp+88h+ppv], rax; ppv
0x14000fbfa  lea     r9, _GUID_b196b28f_bab4_101a_b69c_00aa00341d07; riid
0x14000fc01  xor     r8d, r8d; pvReserved
0x14000fc04  lea     edx, [r8+1]; dwClsContext
0x14000fc08  lea     rcx, [rsp+88h+pclsid]; rclsid
0x14000fc0d  call    cs:__imp_CoGetClassObject
0x14000fc14  nop     dword ptr [rax+rax+00h]
0x14000fc19  mov     edi, eax
0x14000fc1b  test    eax, eax
0x14000fc1d  js      short loc_14000FC48
0x14000fc1f  mov     rcx, [rsp+88h+var_48]
0x14000fc24  mov     rax, [rcx]
0x14000fc27  mov     [rsp+88h+var_60], rsi
0x14000fc2c  mov     [rsp+88h+ppv], rbp
0x14000fc31  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x14000fc38  xor     r8d, r8d
0x14000fc3b  xor     edx, edx
0x14000fc3d  mov     rax, [rax+38h]
0x14000fc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc46  mov     edi, eax
0x14000fc48  mov     rcx, [rsp+88h+var_48]
0x14000fc4d  test    rcx, rcx
0x14000fc50  jz      short loc_14000FC5F
0x14000fc52  mov     rax, [rcx]
0x14000fc55  mov     rax, [rax+10h]
0x14000fc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc5e  nop
0x14000fc5f  jmp     short loc_14000FC86
0x14000fc61  mov     [rsp+88h+ppv], rsi; ppv
0x14000fc66  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14000fc6d  xor     edx, edx; pUnkOuter
0x14000fc6f  lea     r8d, [rdx+1]; dwClsContext
0x14000fc73  lea     rcx, [rsp+88h+pclsid]; rclsid
0x14000fc78  call    cs:__imp_CoCreateInstance
0x14000fc7f  nop     dword ptr [rax+rax+00h]
0x14000fc84  mov     edi, eax
0x14000fc86  mov     eax, edi
0x14000fc88  jmp     short loc_14000FC8C
0x14000fc8a  xor     eax, eax
0x14000fc8c  mov     rcx, [rsp+88h+var_30]
0x14000fc91  xor     rcx, rsp; StackCookie
0x14000fc94  call    __security_check_cookie
0x14000fc99  mov     rbx, [rsp+88h+arg_8]
0x14000fca1  add     rsp, 60h
0x14000fca5  pop     r15
0x14000fca7  pop     r14
0x14000fca9  pop     rdi
0x14000fcaa  pop     rsi
0x14000fcab  pop     rbp
0x14000fcac  retn
```
