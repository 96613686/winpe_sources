# LdrpGenericExceptionFilter

- ea: `0x18015b7c8`
- end: `0x18015b8f0`
- name: `LdrpGenericExceptionFilter`
- size: `296`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x18002dd30`
- `0x1800442f0`
- `0x18004febc`
- `0x180083d30`
- `0x180084370`
- `0x1800847b0`
- `0x1800b6f08`
- `0x1800c8cd0`
- `0x1800d1da0`
- `0x18010a750`

## callees

- `0x180007060`
- `0x18001eb80`
- `0x18004f0d0`
- `0x18013b400`
- `0x18015b7c8`
- `0x18015f060`
- `0x18015f540`

## string_xrefs

- `0x18015b83e`: `Break repeatedly, break Once, Ignore, terminate Process or terminate Thread (boipt)? `

## pseudocode

```c
__int64 __fastcall LdrpGenericExceptionFilter(unsigned int **a1, char a2)
{
  unsigned int v3; // edi
  bool v4; // zf
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  char v9; // [rsp+60h] [rbp+8h] BYREF

  v3 = **a1;
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrutil.c",
    564,
    (int)"LdrpGenericExceptionFilter",
    0,
    "Function %s raised exception 0x%08lx\n\tException record: .exr %p\n\tContext record: .cxr %p\n",
    a2);
  if ( (LdrpDebugFlags & 0x30) == 0x20 )
  {
    while ( 1 )
    {
      DbgPrint("\n***Exception thrown within loader***\n");
      DbgPrompt("Break repeatedly, break Once, Ignore, terminate Process or terminate Thread (boipt)? ", &v9, 2);
      if ( v9 > 98 )
      {
        v5 = v9 - 105;
        v4 = v9 == 105;
      }
      else
      {
        if ( v9 == 98 || v9 == 66 )
          goto LABEL_13;
        v5 = v9 - 73;
        v4 = v9 == 73;
      }
      if ( v4 )
        return 1;
      v6 = v5 - 6;
      if ( !v6 )
      {
LABEL_13:
        DbgPrint("Execute '.cxr %p' to dump context\n", a1[1]);
        __debugbreak();
      }
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 4 )
        {
          LdrpLogFatalLdrEtwEvent(&NtCurrentPeb()->ProcessParameters->ImagePathName, LoaderFatalErrorThread);
          NtTerminateThread(-2, v3);
        }
      }
      else
      {
        LdrpLogFatalLdrEtwEvent(&NtCurrentPeb()->ProcessParameters->ImagePathName, LoaderFatalErrorProc);
        ZwTerminateProcess(-1, v3);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18015b7c8  mov     r11, rsp
0x18015b7cb  mov     [r11+10h], rbx
0x18015b7cf  push    rdi
0x18015b7d0  sub     rsp, 50h
0x18015b7d4  mov     r8, [rcx]
0x18015b7d7  mov     rbx, rcx
0x18015b7da  mov     rax, [rcx+8]
0x18015b7de  xor     r9d, r9d; int
0x18015b7e1  mov     [r11-18h], rax
0x18015b7e5  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18015b7ec  mov     [r11-20h], r8
0x18015b7f0  lea     rax, aFunctionSRaise; "Function %s raised exception 0x%08lx\n"...
0x18015b7f7  mov     edi, [r8]
0x18015b7fa  lea     r8, aLdrpgenericexc; "LdrpGenericExceptionFilter"
0x18015b801  mov     [rsp+58h+var_28], edi
0x18015b805  mov     [r11-30h], rdx
0x18015b809  mov     edx, 234h; int
0x18015b80e  mov     [r11-38h], rax
0x18015b812  call    LdrpLogInternal
0x18015b817  mov     eax, cs:LdrpDebugFlags
0x18015b81d  and     al, 30h
0x18015b81f  cmp     al, 20h ; ' '
0x18015b821  jnz     loc_18015B8DF
0x18015b827  lea     rcx, aExceptionThrow; "\n***Exception thrown within loader***"...
0x18015b82e  call    DbgPrint
0x18015b833  mov     r8d, 2
0x18015b839  lea     rdx, [rsp+58h+arg_0]
0x18015b83e  lea     rcx, aBreakRepeatedl; "Break repeatedly, break Once, Ignore, t"...
0x18015b845  call    DbgPrompt
0x18015b84a  movsx   ecx, [rsp+58h+arg_0]
0x18015b84f  cmp     ecx, 62h ; 'b'
0x18015b852  jg      short loc_18015B860
0x18015b854  jz      short loc_18015B8CE
0x18015b856  sub     ecx, 42h ; 'B'
0x18015b859  jz      short loc_18015B8CE
0x18015b85b  sub     ecx, 7
0x18015b85e  jmp     short loc_18015B863
0x18015b860  sub     ecx, 69h ; 'i'
0x18015b863  jz      short loc_18015B8DF
0x18015b865  sub     ecx, 6
0x18015b868  jz      short loc_18015B8CE
0x18015b86a  sub     ecx, 1
0x18015b86d  jz      short loc_18015B8A1
0x18015b86f  cmp     ecx, 4
0x18015b872  jnz     short loc_18015B827
0x18015b874  mov     rax, gs:60h
0x18015b87d  lea     rdx, LoaderFatalErrorThread
0x18015b884  mov     rcx, [rax+20h]
0x18015b888  add     rcx, 60h ; '`'
0x18015b88c  call    LdrpLogFatalLdrEtwEvent
0x18015b891  mov     edx, edi
0x18015b893  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18015b89a  call    NtTerminateThread
0x18015b89f  jmp     short loc_18015B827
0x18015b8a1  mov     rax, gs:60h
0x18015b8aa  lea     rdx, LoaderFatalErrorProc
0x18015b8b1  mov     rcx, [rax+20h]
0x18015b8b5  add     rcx, 60h ; '`'
0x18015b8b9  call    LdrpLogFatalLdrEtwEvent
0x18015b8be  mov     edx, edi
0x18015b8c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18015b8c4  call    ZwTerminateProcess
0x18015b8c9  jmp     loc_18015B827
0x18015b8ce  mov     rdx, [rbx+8]
0x18015b8d2  lea     rcx, aExecuteCxrPToD; "Execute '.cxr %p' to dump context\n"
0x18015b8d9  call    DbgPrint
0x18015b8de  int     3; Trap to Debugger
0x18015b8df  mov     rbx, [rsp+58h+arg_8]
0x18015b8e4  mov     eax, 1
0x18015b8e9  add     rsp, 50h
0x18015b8ed  pop     rdi
0x18015b8ee  retn
```
