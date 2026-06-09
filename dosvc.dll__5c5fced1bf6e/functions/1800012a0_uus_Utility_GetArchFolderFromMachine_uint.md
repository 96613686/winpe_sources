# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x1800012a0`
- end: `0x18000137a`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800010f0`
- `0x180001170`
- `0x180009d00`

## callees

- `0x1800012a0`
- `0x180001590`
- `0x1800015e0`
- `0x180005b50`
- `0x18000975c`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetArchFolderFromMachine(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 == 34404 )
  {
    v5 = uus::Const::archX64;
    v6 = -1;
    do
      ++v6;
    while ( uus::Const::archX64[v6] );
    goto LABEL_15;
  }
  v3 = a2 - 332;
  if ( !v3 )
  {
    v5 = uus::Const::archX86;
    v6 = -1;
    do
      ++v6;
    while ( uus::Const::archX86[v6] );
    goto LABEL_15;
  }
  v4 = v3 - 116;
  if ( !v4 )
  {
    v5 = uus::Const::archArm;
    v6 = -1;
    do
      ++v6;
    while ( uus::Const::archArm[v6] );
LABEL_15:
    pExceptionObject[0] = v5;
    pExceptionObject[1] = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, pExceptionObject);
    return a1;
  }
  if ( v4 != 43172 )
  {
    std::exception::exception((std::exception *)pExceptionObject, "Unsupported machine architecture");
    pExceptionObject[0] = &std::runtime_error::`vftable';
    throw (std::runtime_error *)pExceptionObject;
  }
  std::filesystem::path::path(a1, &uus::Const::archArm64);
  return a1;
}

```

## disassembly

```asm
0x1800012a0  push    rbx
0x1800012a2  sub     rsp, 50h
0x1800012a6  mov     rbx, rcx
0x1800012a9  cmp     edx, 8664h
0x1800012af  jz      loc_18000133C
0x1800012b5  sub     edx, 14Ch
0x1800012bb  jz      short loc_180001321
0x1800012bd  sub     edx, 74h ; 't'
0x1800012c0  jz      short loc_180001307
0x1800012c2  cmp     edx, 0A8A4h
0x1800012c8  jz      short loc_1800012F9
0x1800012ca  lea     rdx, aUnsupportedMac; "Unsupported machine architecture"
0x1800012d1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800012d6  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1800012db  lea     rax, ??_7runtime_error@std@@6B@; const std::runtime_error::`vftable'
0x1800012e2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800012e9  mov     [rsp+58h+pExceptionObject], rax
0x1800012ee  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800012f3  call    _CxxThrowException_0
0x1800012f9  lea     rdx, ?archArm64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm64
0x180001300  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x180001305  jmp     short loc_180001371
0x180001307  mov     rcx, cs:?archArm@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm
0x18000130e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001315  inc     rax
0x180001318  cmp     word ptr [rcx+rax*2], 0
0x18000131d  jnz     short loc_180001315
0x18000131f  jmp     short loc_18000135A
0x180001321  mov     rcx, cs:?archX86@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX86
0x180001328  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000132f  nop
0x180001330  inc     rax
0x180001333  cmp     word ptr [rcx+rax*2], 0
0x180001338  jnz     short loc_180001330
0x18000133a  jmp     short loc_18000135A
0x18000133c  mov     rcx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180001343  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000134a  nop     word ptr [rax+rax+00h]
0x180001350  inc     rax
0x180001353  cmp     word ptr [rcx+rax*2], 0
0x180001358  jnz     short loc_180001350
0x18000135a  mov     [rsp+58h+pExceptionObject], rcx
0x18000135f  lea     rdx, [rsp+58h+pExceptionObject]
0x180001364  mov     rcx, rbx
0x180001367  mov     [rsp+58h+var_20], rax
0x18000136c  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180001371  mov     rax, rbx
0x180001374  add     rsp, 50h
0x180001378  pop     rbx
0x180001379  retn
```
