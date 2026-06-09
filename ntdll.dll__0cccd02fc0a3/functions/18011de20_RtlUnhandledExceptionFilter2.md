# RtlUnhandledExceptionFilter2

- ea: `0x18011de20`
- end: `0x18011e1f1`
- name: `RtlUnhandledExceptionFilter2`
- size: `977`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800430f0`
- `0x18011ddb8`
- `0x18011de00`
- `0x18015adb0`
- `0x18015ca50`

## callees

- `0x18001a080`
- `0x1800618b8`
- `0x180109270`
- `0x18011de20`

## string_xrefs

- `0x18011df76`: `The resource is owned exclusively by thread %p\n`
- `0x18011df88`: `The resource is owned shared by %d threads\n`
- `0x18011dfcd`: `The critical section is owned by thread %p.\n`
- `0x18011dfdb`: `Go determine why that thread has not released the critical section.\n\n`
- `0x18011e0b2`: `This means the data could not be read, typically because of a bad block on the disk.  Check your hardware.\n\n`
- `0x18011e0e9`: `write to`
- `0x18011e0e2`: `read from`
- `0x18011e0cc`: `\n\n *** An Access Violation occurred in %ws:%s\n\n`
- `0x18011dee3`: `This is usually the result of a memory copy to a local buffer or structure where the size is not properly calculated/checked.\n`
- `0x18011def3`: `If this bug ends up in the shipping product, it could be a severe security hole.\n`

## pseudocode

```c
__int64 __fastcall RtlUnhandledExceptionFilter2(const void **a1)
{
  int v2; // edi
  _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r15
  const wchar_t *Buffer; // r15
  __int64 v5; // rdx
  unsigned int **v6; // rcx
  unsigned int *v7; // r12
  __int64 v8; // r12
  int v9; // r9d
  const void *v10; // r9
  __int64 v11; // rcx
  const char *v12; // rax
  const void *v13; // r9

  v2 = 0;
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  if ( ProcessParameters )
    Buffer = ProcessParameters->CommandLine.Buffer;
  else
    Buffer = L"<unknown>";
  if ( (unsigned __int8)RtlIsAnyDebuggerPresent() )
  {
    v7 = *v6;
    if ( **v6 == -1073741819 )
    {
      DbgPrintEx(101, 0, "\n\n *** An Access Violation occurred in %ws:%s\n\n", Buffer, v5);
      v12 = "write to";
      if ( !*((_QWORD *)*a1 + 4) )
        v12 = "read from";
      DbgPrintEx(101, 0, "The instruction at %p tried to %s ", *((const void **)*a1 + 2), v12);
      v13 = (const void *)*((_QWORD *)*a1 + 5);
      if ( v13 )
        DbgPrintEx(101, 0, "an invalid address, %p\n\n", v13);
      else
        DbgPrintEx(101, 0, "a NULL pointer\n\n");
    }
    else
    {
      switch ( *v7 )
      {
        case 0xC0000006:
          DbgPrintEx(101, 0, "\n\n *** Inpage error in %ws:%s\n\n", Buffer, v5);
          DbgPrintEx(
            101,
            0,
            "The instruction at %p referenced memory at %p.\n",
            *((const void **)*a1 + 2),
            *((const void **)*a1 + 5));
          DbgPrintEx(101, 0, "This failed because of error %Ix.\n\n", *((_QWORD *)*a1 + 6));
          v11 = *((_QWORD *)*a1 + 6);
          switch ( v11 )
          {
            case -1073741670LL:
              DbgPrintEx(
                101,
                0,
                "This means the machine is out of memory.  Use !vm to see where all the memory is being used.\n\n");
              break;
            case -1073741668LL:
            case -1073741462LL:
              DbgPrintEx(
                101,
                0,
                "This means the data could not be read, typically because of a bad block on the disk.  Check your hardware.\n\n");
              break;
            case -1073741435LL:
              DbgPrintEx(101, 0, "This means that the I/O device reported an I/O error.  Check your hardware.");
              break;
          }
          break;
        case 0xC0000194:
          v8 = *((_QWORD *)v7 + 4);
          if ( v8 )
          {
            if ( *(_QWORD *)v8 && **(_WORD **)v8 == 1 )
            {
              DbgPrintEx(101, 0, "\n\n *** Resource timeout (%p) in %ws:%s\n\n", v8, Buffer, v5);
              v9 = *(_DWORD *)(v8 + 68);
              if ( v9 >= 0 )
              {
                if ( v9 <= 0 )
                  DbgPrintEx(
                    101,
                    0,
                    "The resource is unowned.  This usually implies a slow-moving machine due to memory pressure\n\n");
                else
                  DbgPrintEx(101, 0, "The resource is owned shared by %d threads\n", v9);
              }
              else
              {
                DbgPrintEx(101, 0, "The resource is owned exclusively by thread %p\n", *(const void **)(v8 + 72));
              }
            }
            else
            {
              DbgPrintEx(101, 0, "\n\n *** Critical Section Timeout (%p) in %ws:%s\n\n", v8, Buffer, v5);
              v10 = *(const void **)(v8 + 16);
              if ( v10 )
              {
                DbgPrintEx(101, 0, "The critical section is owned by thread %p.\n", v10);
                DbgPrintEx(101, 0, "Go determine why that thread has not released the critical section.\n\n");
              }
              else
              {
                DbgPrintEx(
                  101,
                  0,
                  "The critical section is unowned.  This usually implies a slow-moving machine due to memory pressure\n"
                  "\n");
              }
            }
          }
          break;
        case 0xC0000409:
          DbgPrintEx(101, 0, "\n\n *** A stack buffer overrun occurred in %ws:%s\n\n", Buffer, v5);
          DbgPrintEx(
            101,
            0,
            "This is usually the result of a memory copy to a local buffer or structure where the size is not properly ca"
            "lculated/checked.\n");
          DbgPrintEx(101, 0, "If this bug ends up in the shipping product, it could be a severe security hole.\n");
          DbgPrintEx(
            101,
            0,
            "The stack trace should show the guilty function (the function directly above __report_gsfailure).\n");
          break;
        default:
          DbgPrintEx(101, 0, "\n\n *** Unhandled exception 0x%08lx, hit in %ws:%s\n\n", *v7, Buffer, v5);
          break;
      }
    }
    DbgPrintEx(101, 0, " *** enter .exr %p for the exception record\n", *a1);
    if ( *(_DWORD *)*a1 != -1073740791 )
      DbgPrintEx(101, 0, " ***  enter .cxr %p for the context\n", a1[1]);
    DbgPrintEx(101, 0, " *** then kb to get the faulting stack\n\n");
    __debugbreak();
  }
  if ( *(_DWORD *)*a1 == -1073740791 )
    RtlReportException(*a1, a1[1], 0);
  LOBYTE(v2) = *(_DWORD *)*a1 != -1073741420;
  return (unsigned int)(v2 - 1);
}

```

## disassembly

```asm
0x18011de20  mov     [rsp+arg_8], rdx
0x18011de25  mov     [rsp+arg_0], rcx
0x18011de2a  push    rbx
0x18011de2b  push    rsi
0x18011de2c  push    rdi
0x18011de2d  push    r12
0x18011de2f  push    r13
0x18011de31  push    r14
0x18011de33  push    r15
0x18011de35  sub     rsp, 40h
0x18011de39  mov     r13, rdx
0x18011de3c  mov     r14, rcx
0x18011de3f  xor     edi, edi
0x18011de41  mov     rax, gs:60h
0x18011de4a  mov     r15, [rax+20h]
0x18011de4e  test    r15, r15
0x18011de51  jz      short loc_18011DE59
0x18011de53  mov     r15, [r15+78h]
0x18011de57  jmp     short loc_18011DE60
0x18011de59  lea     r15, aUnknown_0; "<unknown>"
0x18011de60  mov     [rsp+78h+var_48], r15
0x18011de65  call    RtlIsAnyDebuggerPresent
0x18011de6a  test    al, al
0x18011de6c  jz      loc_18011E1B3
0x18011de72  mov     r12, [rcx]
0x18011de75  cmp     dword ptr [r12], 0C0000005h
0x18011de7d  jz      loc_18011E0C4
0x18011de83  cmp     dword ptr [r12], 0C0000006h
0x18011de8b  jz      loc_18011E025
0x18011de91  cmp     dword ptr [r12], 0C0000194h
0x18011de99  jz      short loc_18011DF0F
0x18011de9b  mov     ebx, 65h ; 'e'
0x18011dea0  mov     ecx, ebx
0x18011dea2  cmp     dword ptr [r12], 0C0000409h
0x18011deaa  jz      short loc_18011DECD
0x18011deac  mov     [rsp+78h+var_50], rdx
0x18011deb1  mov     [rsp+78h+var_58], r15
0x18011deb6  mov     r9d, [r12]
0x18011deba  lea     r8, aUnhandledExcep; "\n\n *** Unhandled exception 0x%08lx, h"...
0x18011dec1  xor     edx, edx
0x18011dec3  call    DbgPrintEx
0x18011dec8  jmp     loc_18011E13F
0x18011decd  mov     [rsp+78h+var_58], rdx
0x18011ded2  mov     r9, r15
0x18011ded5  lea     r8, aAStackBufferOv; "\n\n *** A stack buffer overrun occurre"...
0x18011dedc  xor     edx, edx
0x18011dede  call    DbgPrintEx
0x18011dee3  lea     r8, aThisIsUsuallyT; "This is usually the result of a memory "...
0x18011deea  xor     edx, edx
0x18011deec  mov     ecx, ebx
0x18011deee  call    DbgPrintEx
0x18011def3  lea     r8, aIfThisBugEndsU; "If this bug ends up in the shipping pro"...
0x18011defa  xor     edx, edx
0x18011defc  mov     ecx, ebx
0x18011defe  call    DbgPrintEx
0x18011df03  lea     r8, aTheStackTraceS; "The stack trace should show the guilty "...
0x18011df0a  jmp     loc_18011E136
0x18011df0f  mov     r12, [r12+20h]
0x18011df14  test    r12, r12
0x18011df17  jz      loc_18011E01B
0x18011df1d  mov     rax, [r12]
0x18011df21  mov     [rsp+78h+var_40], rax
0x18011df26  mov     esi, 1
0x18011df2b  test    rax, rax
0x18011df2e  jz      short loc_18011DFA1
0x18011df30  cmp     [rax], si
0x18011df33  jnz     short loc_18011DFA1
0x18011df35  mov     [rsp+78h+var_50], rdx
0x18011df3a  mov     [rsp+78h+var_58], r15
0x18011df3f  mov     r9, r12
0x18011df42  lea     r8, aResourceTimeou; "\n\n *** Resource timeout (%p) in %ws:%"...
0x18011df49  xor     edx, edx
0x18011df4b  lea     ebx, [rsi+64h]
0x18011df4e  mov     ecx, ebx
0x18011df50  call    DbgPrintEx
0x18011df55  mov     r9d, [r12+44h]
0x18011df5a  mov     [rsp+78h+arg_18], r9d
0x18011df62  mov     [rsp+78h+arg_10], r9d
0x18011df6a  mov     ecx, ebx
0x18011df6c  test    r9d, r9d
0x18011df6f  jns     short loc_18011DF86
0x18011df71  mov     r9, [r12+48h]
0x18011df76  lea     r8, aTheResourceIsO; "The resource is owned exclusively by th"...
0x18011df7d  xor     edx, edx
0x18011df7f  call    DbgPrintEx
0x18011df84  jmp     short loc_18011DFF4
0x18011df86  jle     short loc_18011DF98
0x18011df88  lea     r8, aTheResourceIsO_0; "The resource is owned shared by %d thre"...
0x18011df8f  xor     edx, edx
0x18011df91  call    DbgPrintEx
0x18011df96  jmp     short loc_18011DFF4
0x18011df98  lea     r8, aTheResourceIsU; "The resource is unowned.  This usually "...
0x18011df9f  jmp     short loc_18011DFED
0x18011dfa1  mov     [rsp+78h+var_50], rdx
0x18011dfa6  mov     [rsp+78h+var_58], r15
0x18011dfab  mov     r9, r12
0x18011dfae  lea     r8, aCriticalSectio_1; "\n\n *** Critical Section Timeout (%p) "...
0x18011dfb5  xor     edx, edx
0x18011dfb7  lea     ebx, [rdx+65h]
0x18011dfba  mov     ecx, ebx
0x18011dfbc  call    DbgPrintEx
0x18011dfc1  mov     r9, [r12+10h]
0x18011dfc6  mov     ecx, ebx
0x18011dfc8  test    r9, r9
0x18011dfcb  jz      short loc_18011DFE6
0x18011dfcd  lea     r8, aTheCriticalSec; "The critical section is owned by thread"...
0x18011dfd4  xor     edx, edx
0x18011dfd6  call    DbgPrintEx
0x18011dfdb  lea     r8, aGoDetermineWhy; "Go determine why that thread has not re"...
0x18011dfe2  mov     ecx, ebx
0x18011dfe4  jmp     short loc_18011DFED
0x18011dfe6  lea     r8, aTheCriticalSec_0; "The critical section is unowned.  This "...
0x18011dfed  xor     edx, edx
0x18011dfef  call    DbgPrintEx
0x18011dff4  jmp     loc_18011E144
0x18011dff9  xor     edi, edi
0x18011dffb  lea     ebx, [rdi+65h]
0x18011dffe  lea     esi, [rdi+1]
0x18011e001  mov     r13, [rsp+78h+arg_8]
0x18011e009  mov     r14, [rsp+78h+arg_0]
0x18011e011  mov     r15, [rsp+78h+var_48]
0x18011e016  jmp     loc_18011E144
0x18011e01b  mov     ebx, 65h ; 'e'
0x18011e020  jmp     loc_18011E13F
0x18011e025  mov     [rsp+78h+var_58], rdx
0x18011e02a  mov     r9, r15
0x18011e02d  lea     r8, aInpageErrorInW; "\n\n *** Inpage error in %ws:%s\n\n"
0x18011e034  xor     edx, edx
0x18011e036  lea     ebx, [rdx+65h]
0x18011e039  mov     ecx, ebx
0x18011e03b  call    DbgPrintEx
0x18011e040  mov     r9, [r14]
0x18011e043  mov     rax, [r9+28h]
0x18011e047  mov     [rsp+78h+var_58], rax
0x18011e04c  mov     r9, [r9+10h]
0x18011e050  lea     r8, aTheInstruction; "The instruction at %p referenced memory"...
0x18011e057  xor     edx, edx
0x18011e059  mov     ecx, ebx
0x18011e05b  call    DbgPrintEx
0x18011e060  mov     r9, [r14]
0x18011e063  mov     r9, [r9+30h]
0x18011e067  lea     r8, aThisFailedBeca; "This failed because of error %Ix.\n\n"
0x18011e06e  xor     edx, edx
0x18011e070  mov     ecx, ebx
0x18011e072  call    DbgPrintEx
0x18011e077  mov     rax, [r14]
0x18011e07a  mov     rcx, [rax+30h]
0x18011e07e  cmp     rcx, 0FFFFFFFFC000009Ah
0x18011e085  jz      short loc_18011E0BB
0x18011e087  cmp     rcx, 0FFFFFFFFC000009Ch
0x18011e08e  jz      short loc_18011E0B2
0x18011e090  cmp     rcx, 0FFFFFFFFC000016Ah
0x18011e097  jz      short loc_18011E0B2
0x18011e099  cmp     rcx, 0FFFFFFFFC0000185h
0x18011e0a0  jnz     loc_18011E13F
0x18011e0a6  lea     r8, aThisMeansThatT; "This means that the I/O device reported"...
0x18011e0ad  jmp     loc_18011E136
0x18011e0b2  lea     r8, aThisMeansTheDa; "This means the data could not be read, "...
0x18011e0b9  jmp     short loc_18011E136
0x18011e0bb  lea     r8, aThisMeansTheMa; "This means the machine is out of memory"...
0x18011e0c2  jmp     short loc_18011E136
0x18011e0c4  mov     [rsp+78h+var_58], rdx
0x18011e0c9  mov     r9, r15
0x18011e0cc  lea     r8, aAnAccessViolat; "\n\n *** An Access Violation occurred i"...
0x18011e0d3  xor     edx, edx
0x18011e0d5  lea     ebx, [rdx+65h]
0x18011e0d8  mov     ecx, ebx
0x18011e0da  call    DbgPrintEx
0x18011e0df  mov     r9, [r14]
0x18011e0e2  lea     rcx, aReadFrom; "read from"
0x18011e0e9  lea     rax, aWriteTo; "write to"
0x18011e0f0  cmp     [r9+20h], rdi
0x18011e0f4  cmovz   rax, rcx
0x18011e0f8  mov     [rsp+78h+var_58], rax
0x18011e0fd  mov     r9, [r9+10h]
0x18011e101  lea     r8, aTheInstruction_0; "The instruction at %p tried to %s "
0x18011e108  xor     edx, edx
0x18011e10a  mov     ecx, ebx
0x18011e10c  call    DbgPrintEx
0x18011e111  mov     rax, [r14]
0x18011e114  mov     r9, [rax+28h]
0x18011e118  test    r9, r9
0x18011e11b  jz      short loc_18011E12F
0x18011e11d  lea     r8, aAnInvalidAddre; "an invalid address, %p\n\n"
0x18011e124  xor     edx, edx
0x18011e126  mov     ecx, ebx
0x18011e128  call    DbgPrintEx
0x18011e12d  jmp     short loc_18011E13F
0x18011e12f  lea     r8, aANullPointer; "a NULL pointer\n\n"
0x18011e136  xor     edx, edx
0x18011e138  mov     ecx, ebx
0x18011e13a  call    DbgPrintEx
0x18011e13f  mov     esi, 1
0x18011e144  mov     r9, [r14]
0x18011e147  lea     r8, aEnterExrPForTh; " *** enter .exr %p for the exception re"...
0x18011e14e  xor     edx, edx
0x18011e150  mov     ecx, ebx
0x18011e152  call    DbgPrintEx
0x18011e157  mov     rax, [r14]
0x18011e15a  cmp     dword ptr [rax], 0C0000409h
0x18011e160  jz      short loc_18011E176
0x18011e162  mov     r9, [r14+8]
0x18011e166  lea     r8, aEnterCxrPForTh; " ***  enter .cxr %p for the context\n"
0x18011e16d  xor     edx, edx
0x18011e16f  mov     ecx, ebx
0x18011e171  call    DbgPrintEx
0x18011e176  lea     r8, aThenKbToGetThe; " *** then kb to get the faulting stack"...
0x18011e17d  xor     edx, edx
0x18011e17f  mov     ecx, ebx
0x18011e181  call    DbgPrintEx
0x18011e186  int     3; Trap to Debugger
0x18011e187  mov     r9, [r14]
0x18011e18a  cmp     dword ptr [r9], 0C0000194h
0x18011e191  jnz     short loc_18011E1B8
0x18011e193  mov     [rsp+78h+var_50], r13
0x18011e198  mov     [rsp+78h+var_58], r15
0x18011e19d  mov     r9, [r9+20h]
0x18011e1a1  lea     r8, aRestartingWait; " *** Restarting wait on critsec or reso"...
0x18011e1a8  xor     edx, edx
0x18011e1aa  mov     ecx, ebx
0x18011e1ac  call    DbgPrintEx
0x18011e1b1  jmp     short loc_18011E1B8
0x18011e1b3  mov     esi, 1
0x18011e1b8  mov     rcx, [r14]
0x18011e1bb  cmp     dword ptr [rcx], 0C0000409h
0x18011e1c1  jnz     short loc_18011E1CF
0x18011e1c3  xor     r8d, r8d
0x18011e1c6  mov     rdx, [r14+8]
0x18011e1ca  call    RtlReportException
0x18011e1cf  mov     rcx, [r14]
0x18011e1d2  cmp     dword ptr [rcx], 0C0000194h
0x18011e1d8  setnz   dil
0x18011e1dc  sub     edi, esi
0x18011e1de  mov     eax, edi
0x18011e1e0  add     rsp, 40h
0x18011e1e4  pop     r15
0x18011e1e6  pop     r14
0x18011e1e8  pop     r13
0x18011e1ea  pop     r12
0x18011e1ec  pop     rdi
0x18011e1ed  pop     rsi
0x18011e1ee  pop     rbx
0x18011e1ef  retn
```
