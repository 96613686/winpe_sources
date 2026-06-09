# NgcUtils::GenRandom(uchar *,ulong)

- ea: `0x180013f54`
- end: `0x180013f94`
- name: `?GenRandom@NgcUtils@@YAJPEAEK@Z`
- size: `64`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013f9c`
- `0x18001ba2c`

## callees

- `0x18001368c`
- `0x180013f54`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180013f66`
- `bcrypt!BCryptGenRandom` at `0x180013f66`

## string_xrefs

- `0x180013f75`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::GenRandom(PUCHAR pbBuffer, ULONG cbBuffer, __int64 a3, __int64 a4, int a5)
{
  NTSTATUS v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = BCryptGenRandom(0, pbBuffer, cbBuffer, 2u);
  if ( v5 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x57,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v5,
             a5);
}

```

## disassembly

```asm
0x180013f54  sub     rsp, 28h
0x180013f58  mov     r8d, edx; cbBuffer
0x180013f5b  mov     r9d, 2; dwFlags
0x180013f61  mov     rdx, rcx; pbBuffer
0x180013f64  xor     ecx, ecx; hAlgorithm
0x180013f66  call    cs:__imp_BCryptGenRandom
0x180013f6c  test    eax, eax
0x180013f6e  jns     short loc_180013F8D
0x180013f70  mov     rcx, [rsp+28h]; this
0x180013f75  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013f7c  mov     r9d, eax; char *
0x180013f7f  mov     edx, 57h ; 'W'; void *
0x180013f84  add     rsp, 28h
0x180013f88  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013f8d  xor     eax, eax
0x180013f8f  add     rsp, 28h
0x180013f93  retn
```
