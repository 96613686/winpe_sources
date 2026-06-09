# _commit

- ea: `0x18001c1d0`
- end: `0x18001c265`
- name: `_commit`
- size: `149`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bc50`

## callees

- `0x180014f34`
- `0x1800150d0`
- `0x18001c13c`
- `0x18001c1d0`

## pseudocode

```c
int __cdecl commit(int FileHandle)
{
  int *v2; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+40h] [rbp+8h] BYREF
  char v4; // [rsp+48h] [rbp+10h] BYREF
  int v5; // [rsp+50h] [rbp+18h] BYREF
  int v6; // [rsp+58h] [rbp+20h] BYREF

  v3 = FileHandle;
  if ( FileHandle == -2 )
  {
    *errno() = 9;
  }
  else
  {
    if ( FileHandle >= 0
      && FileHandle < (unsigned int)nhandle
      && (*(_BYTE *)(_pioinfo[(__int64)FileHandle >> 6] + 72LL * (FileHandle & 0x3F) + 56) & 1) != 0 )
    {
      v5 = FileHandle;
      v6 = FileHandle;
      v2 = &v3;
      return ((__int64 (__fastcall *)(char *, int *, int **, int *))_crt_seh_guarded_call_int_::operator()__lambda_a37b2b86f63e897a80ea819b0eb08c01___lambda_38ce7e780aa69e748d6df282ebc68efe_____lambda_99fb1378e971ab6e7edea83e3a7a83a2___)(
               &v4,
               &v6,
               &v2,
               &v5);
    }
    *errno() = 9;
    invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x18001c1d0  mov     [rsp+arg_0], ecx
0x18001c1d4  sub     rsp, 38h
0x18001c1d8  movsxd  r8, ecx
0x18001c1db  cmp     r8d, 0FFFFFFFEh
0x18001c1df  jnz     short loc_18001C1EE
0x18001c1e1  call    _errno
0x18001c1e6  mov     dword ptr [rax], 9
0x18001c1ec  jmp     short loc_18001C25D
0x18001c1ee  test    ecx, ecx
0x18001c1f0  js      short loc_18001C24D
0x18001c1f2  cmp     r8d, cs:_nhandle
0x18001c1f9  jnb     short loc_18001C24D
0x18001c1fb  mov     eax, r8d
0x18001c1fe  lea     r9, __pioinfo
0x18001c205  and     eax, 3Fh
0x18001c208  mov     rdx, r8
0x18001c20b  sar     rdx, 6
0x18001c20f  lea     rcx, [rax+rax*8]
0x18001c213  mov     rax, [r9+rdx*8]
0x18001c217  test    byte ptr [rax+rcx*8+38h], 1
0x18001c21c  jz      short loc_18001C24D
0x18001c21e  lea     rax, [rsp+38h+arg_0]
0x18001c223  mov     [rsp+38h+arg_10], r8d
0x18001c228  mov     [rsp+38h+arg_18], r8d
0x18001c22d  lea     r9, [rsp+38h+arg_10]
0x18001c232  lea     r8, [rsp+38h+var_18]
0x18001c237  mov     [rsp+38h+var_18], rax
0x18001c23c  lea     rdx, [rsp+38h+arg_18]
0x18001c241  lea     rcx, [rsp+38h+arg_8]
0x18001c246  call    __crt_seh_guarded_call_int___operator____lambda_a37b2b86f63e897a80ea819b0eb08c01___lambda_38ce7e780aa69e748d6df282ebc68efe_____lambda_99fb1378e971ab6e7edea83e3a7a83a2___
0x18001c24b  jmp     short loc_18001C260
0x18001c24d  call    _errno
0x18001c252  mov     dword ptr [rax], 9
0x18001c258  call    _invalid_parameter_noinfo
0x18001c25d  or      eax, 0FFFFFFFFh
0x18001c260  add     rsp, 38h
0x18001c264  retn
```
