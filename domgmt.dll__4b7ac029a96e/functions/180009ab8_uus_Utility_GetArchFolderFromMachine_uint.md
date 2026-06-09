# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x180009ab8`
- end: `0x180009b7e`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009f54`

## callees

- `0x180002990`
- `0x180007504`
- `0x180008b80`
- `0x180009ab8`

## pseudocode

```c
_QWORD *__fastcall uus::Utility::GetArchFolderFromMachine(_QWORD *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const char *v5; // rdx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-20h] BYREF

  v3 = a2 - 332;
  if ( v3 )
  {
    v4 = v3 - 116;
    if ( v4 )
    {
      v5 = (const char *)(unsigned int)(v4 - 33956);
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 != 9216 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v5);
          throw (std::runtime_error *)pExceptionObject;
        }
        v6 = uus::Const::archArm64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archArm64[v7] );
      }
      else
      {
        v6 = uus::Const::archX64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archX64[v7] );
      }
    }
    else
    {
      v6 = uus::Const::archArm;
      v7 = -1;
      do
        ++v7;
      while ( uus::Const::archArm[v7] );
    }
  }
  else
  {
    v6 = uus::Const::archX86;
    v7 = -1;
    do
      ++v7;
    while ( uus::Const::archX86[v7] );
  }
  pExceptionObject[0] = v6;
  pExceptionObject[1] = v7;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, (__int64)pExceptionObject);
  return a1;
}

```

## disassembly

```asm
0x180009ab8  mov     [rsp-8+arg_0], rbx
0x180009abd  push    rbp
0x180009abe  mov     rbp, rsp
0x180009ac1  sub     rsp, 50h
0x180009ac5  xor     r8d, r8d
0x180009ac8  mov     rbx, rcx
0x180009acb  sub     edx, 14Ch
0x180009ad1  jz      short loc_180009B2D
0x180009ad3  sub     edx, 74h ; 't'
0x180009ad6  jz      short loc_180009B16
0x180009ad8  sub     edx, 84A4h; char *
0x180009ade  jz      short loc_180009AFF
0x180009ae0  cmp     edx, 2400h
0x180009ae6  jnz     short loc_180009B64
0x180009ae8  mov     rcx, cs:?archArm64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm64
0x180009aef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009af3  inc     rax
0x180009af6  cmp     [rcx+rax*2], r8w
0x180009afb  jnz     short loc_180009AF3
0x180009afd  jmp     short loc_180009B42
0x180009aff  mov     rcx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180009b06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b0a  inc     rax
0x180009b0d  cmp     [rcx+rax*2], r8w
0x180009b12  jnz     short loc_180009B0A
0x180009b14  jmp     short loc_180009B42
0x180009b16  mov     rcx, cs:?archArm@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm
0x180009b1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b21  inc     rax
0x180009b24  cmp     [rcx+rax*2], r8w
0x180009b29  jnz     short loc_180009B21
0x180009b2b  jmp     short loc_180009B42
0x180009b2d  mov     rcx, cs:?archX86@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX86
0x180009b34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b38  inc     rax
0x180009b3b  cmp     [rcx+rax*2], r8w
0x180009b40  jnz     short loc_180009B38
0x180009b42  mov     [rbp+pExceptionObject], rcx
0x180009b46  lea     rdx, [rbp+pExceptionObject]
0x180009b4a  mov     rcx, rbx; void *
0x180009b4d  mov     [rbp+var_18], rax
0x180009b51  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180009b56  mov     rax, rbx
0x180009b59  mov     rbx, [rsp+50h+arg_0]
0x180009b5e  add     rsp, 50h
0x180009b62  pop     rbp
0x180009b63  retn
0x180009b64  lea     rcx, [rbp+pExceptionObject]; this
0x180009b68  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180009b6d  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180009b74  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009b78  call    _CxxThrowException_0
```
