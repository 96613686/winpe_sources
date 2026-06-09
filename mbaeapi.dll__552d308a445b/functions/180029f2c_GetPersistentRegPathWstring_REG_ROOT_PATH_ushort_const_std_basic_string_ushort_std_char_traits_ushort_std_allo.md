# GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180029f2c`
- end: `0x18002a00c`
- name: `?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b068`
- `0x18002f5c4`
- `0x180049050`
- `0x180057ce0`
- `0x180057f6c`
- `0x18005811c`

## callees

- `0x1800024e0`
- `0x1800171b8`
- `0x180029524`
- `0x180029f2c`
- `0x18002b1f0`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x180029fa0`
- `MobileNetworking!GetPersistentRegPath` at `0x180029fa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPersistentRegPathWstring(unsigned int a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // edi
  __int128 *p_Src; // r9
  unsigned int PersistentRegPath; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  int v12; // [rsp+20h] [rbp-58h] BYREF
  __int128 Src; // [rsp+28h] [rbp-50h] BYREF
  __m128i si128; // [rsp+38h] [rbp-40h]

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v6 = 0;
  v12 = 512;
  try
  {
    do
    {
      std::wstring::resize(&Src);
      p_Src = &Src;
      if ( si128.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      PersistentRegPath = GetPersistentRegPath(a1, a2, &v12, p_Src);
      v9 = PersistentRegPath;
      if ( PersistentRegPath != 234 )
        break;
      v10 = v6++;
    }
    while ( v10 < 3 );
    if ( !PersistentRegPath )
    {
      std::wstring::resize(&Src);
      std::wstring::operator=(a3, &Src);
    }
    std::wstring::~wstring((char **)&Src);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v9;
}

```

## disassembly

```asm
0x180029f2c  push    rbx
0x180029f2e  push    rsi
0x180029f2f  push    rdi
0x180029f30  push    r14
0x180029f32  push    r15
0x180029f34  sub     rsp, 50h
0x180029f38  mov     rax, cs:__security_cookie
0x180029f3f  xor     rax, rsp
0x180029f42  mov     [rsp+78h+var_30], rax
0x180029f47  mov     rsi, r8
0x180029f4a  mov     r15, rdx
0x180029f4d  mov     r14d, ecx
0x180029f50  xorps   xmm0, xmm0
0x180029f53  movups  [rsp+78h+Src], xmm0
0x180029f58  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180029f60  movdqu  [rsp+78h+var_40], xmm1
0x180029f66  xor     eax, eax
0x180029f68  mov     word ptr [rsp+78h+Src], ax
0x180029f6d  xor     edi, edi
0x180029f6f  mov     eax, 200h
0x180029f74  mov     [rsp+78h+var_58], eax
0x180029f78  mov     edx, eax
0x180029f7a  lea     rcx, [rsp+78h+Src]; Src
0x180029f7f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180029f84  lea     r9, [rsp+78h+Src]
0x180029f89  cmp     qword ptr [rsp+78h+var_40+8], 7
0x180029f8f  cmova   r9, qword ptr [rsp+78h+Src]
0x180029f95  lea     r8, [rsp+78h+var_58]
0x180029f9a  mov     rdx, r15
0x180029f9d  mov     ecx, r14d
0x180029fa0  call    cs:__imp_GetPersistentRegPath
0x180029fa6  mov     ebx, eax
0x180029fa8  cmp     eax, 0EAh
0x180029fad  jnz     short loc_180029FBE
0x180029faf  mov     ecx, edi
0x180029fb1  inc     edi
0x180029fb3  cmp     ecx, 3
0x180029fb6  jnb     short loc_180029FBE
0x180029fb8  mov     eax, [rsp+78h+var_58]
0x180029fbc  jmp     short loc_180029F78
0x180029fbe  test    eax, eax
0x180029fc0  jnz     short loc_180029FE0
0x180029fc2  mov     edx, [rsp+78h+var_58]
0x180029fc6  dec     edx
0x180029fc8  lea     rcx, [rsp+78h+Src]; Src
0x180029fcd  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180029fd2  lea     rdx, [rsp+78h+Src]
0x180029fd7  mov     rcx, rsi
0x180029fda  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029fdf  nop
0x180029fe0  lea     rcx, [rsp+78h+Src]
0x180029fe5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029fea  nop
0x180029feb  jmp     short loc_180029FF1
0x180029fed  mov     ebx, [rsp+78h+var_58]
0x180029ff1  mov     eax, ebx
0x180029ff3  mov     rcx, [rsp+78h+var_30]
0x180029ff8  xor     rcx, rsp; StackCookie
0x180029ffb  call    __security_check_cookie
0x18002a000  add     rsp, 50h
0x18002a004  pop     r15
0x18002a006  pop     r14
0x18002a008  pop     rdi
0x18002a009  pop     rsi
0x18002a00a  pop     rbx
0x18002a00b  retn
```
