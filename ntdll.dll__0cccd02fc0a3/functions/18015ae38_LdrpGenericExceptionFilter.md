# LdrpGenericExceptionFilter

- ea: `0x18015ae38`
- end: `0x18015af60`
- name: `LdrpGenericExceptionFilter`
- size: `296`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x18002ea30`
- `0x18003e9a0`
- `0x180067350`
- `0x180067990`
- `0x180067dd0`
- `0x1800ac3d0`
- `0x1800c4790`
- `0x1800d0670`
- `0x1800d5cac`
- `0x1801097c0`

## callees

- `0x180007060`
- `0x18001eb80`
- `0x180041584`
- `0x18013aa70`
- `0x18015ae38`
- `0x18015e850`
- `0x18015ed30`

## string_xrefs

- `0x18015aeae`: `Break repeatedly, break Once, Ignore, terminate Process or terminate Thread (boipt)? `

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
0x18015ae38  mov     r11, rsp
0x18015ae3b  mov     [r11+10h], rbx
0x18015ae3f  push    rdi
0x18015ae40  sub     rsp, 50h
0x18015ae44  mov     r8, [rcx]
0x18015ae47  mov     rbx, rcx
0x18015ae4a  mov     rax, [rcx+8]
0x18015ae4e  xor     r9d, r9d; int
0x18015ae51  mov     [r11-18h], rax
0x18015ae55  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18015ae5c  mov     [r11-20h], r8
0x18015ae60  lea     rax, aFunctionSRaise; "Function %s raised exception 0x%08lx\n"...
0x18015ae67  mov     edi, [r8]
0x18015ae6a  lea     r8, aLdrpgenericexc; "LdrpGenericExceptionFilter"
0x18015ae71  mov     [rsp+58h+var_28], edi
0x18015ae75  mov     [r11-30h], rdx
0x18015ae79  mov     edx, 234h; int
0x18015ae7e  mov     [r11-38h], rax
0x18015ae82  call    LdrpLogInternal
0x18015ae87  mov     eax, cs:LdrpDebugFlags
0x18015ae8d  and     al, 30h
0x18015ae8f  cmp     al, 20h ; ' '
0x18015ae91  jnz     loc_18015AF4F
0x18015ae97  lea     rcx, aExceptionThrow; "\n***Exception thrown within loader***"...
0x18015ae9e  call    DbgPrint
0x18015aea3  mov     r8d, 2
0x18015aea9  lea     rdx, [rsp+58h+arg_0]
0x18015aeae  lea     rcx, aBreakRepeatedl; "Break repeatedly, break Once, Ignore, t"...
0x18015aeb5  call    DbgPrompt
0x18015aeba  movsx   ecx, [rsp+58h+arg_0]
0x18015aebf  cmp     ecx, 62h ; 'b'
0x18015aec2  jg      short loc_18015AED0
0x18015aec4  jz      short loc_18015AF3E
0x18015aec6  sub     ecx, 42h ; 'B'
0x18015aec9  jz      short loc_18015AF3E
0x18015aecb  sub     ecx, 7
0x18015aece  jmp     short loc_18015AED3
0x18015aed0  sub     ecx, 69h ; 'i'
0x18015aed3  jz      short loc_18015AF4F
0x18015aed5  sub     ecx, 6
0x18015aed8  jz      short loc_18015AF3E
0x18015aeda  sub     ecx, 1
0x18015aedd  jz      short loc_18015AF11
0x18015aedf  cmp     ecx, 4
0x18015aee2  jnz     short loc_18015AE97
0x18015aee4  mov     rax, gs:60h
0x18015aeed  lea     rdx, LoaderFatalErrorThread
0x18015aef4  mov     rcx, [rax+20h]
0x18015aef8  add     rcx, 60h ; '`'
0x18015aefc  call    LdrpLogFatalLdrEtwEvent
0x18015af01  mov     edx, edi
0x18015af03  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18015af0a  call    NtTerminateThread
0x18015af0f  jmp     short loc_18015AE97
0x18015af11  mov     rax, gs:60h
0x18015af1a  lea     rdx, LoaderFatalErrorProc
0x18015af21  mov     rcx, [rax+20h]
0x18015af25  add     rcx, 60h ; '`'
0x18015af29  call    LdrpLogFatalLdrEtwEvent
0x18015af2e  mov     edx, edi
0x18015af30  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18015af34  call    ZwTerminateProcess
0x18015af39  jmp     loc_18015AE97
0x18015af3e  mov     rdx, [rbx+8]
0x18015af42  lea     rcx, aExecuteCxrPToD; "Execute '.cxr %p' to dump context\n"
0x18015af49  call    DbgPrint
0x18015af4e  int     3; Trap to Debugger
0x18015af4f  mov     rbx, [rsp+58h+arg_8]
0x18015af54  mov     eax, 1
0x18015af59  add     rsp, 50h
0x18015af5d  pop     rdi
0x18015af5e  retn
```
