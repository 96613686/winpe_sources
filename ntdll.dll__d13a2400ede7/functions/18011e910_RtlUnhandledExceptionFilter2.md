# RtlUnhandledExceptionFilter2

- ea: `0x18011e910`
- end: `0x18011ece1`
- name: `RtlUnhandledExceptionFilter2`
- size: `977`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005fce0`
- `0x18011e8a8`
- `0x18011e8f0`
- `0x18015b740`
- `0x18015d260`

## callees

- `0x18001a080`
- `0x18007e298`
- `0x18010a200`
- `0x18011e910`

## string_xrefs

- `0x18011ea66`: `The resource is owned exclusively by thread %p\n`
- `0x18011ea78`: `The resource is owned shared by %d threads\n`
- `0x18011eabd`: `The critical section is owned by thread %p.\n`
- `0x18011eacb`: `Go determine why that thread has not released the critical section.\n\n`
- `0x18011eba2`: `This means the data could not be read, typically because of a bad block on the disk.  Check your hardware.\n\n`
- `0x18011ebd9`: `write to`
- `0x18011ebd2`: `read from`
- `0x18011ebbc`: `\n\n *** An Access Violation occurred in %ws:%s\n\n`
- `0x18011e9d3`: `This is usually the result of a memory copy to a local buffer or structure where the size is not properly calculated/checked.\n`
- `0x18011e9e3`: `If this bug ends up in the shipping product, it could be a severe security hole.\n`

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
0x18011e910  mov     [rsp+arg_8], rdx
0x18011e915  mov     [rsp+arg_0], rcx
0x18011e91a  push    rbx
0x18011e91b  push    rsi
0x18011e91c  push    rdi
0x18011e91d  push    r12
0x18011e91f  push    r13
0x18011e921  push    r14
0x18011e923  push    r15
0x18011e925  sub     rsp, 40h
0x18011e929  mov     r13, rdx
0x18011e92c  mov     r14, rcx
0x18011e92f  xor     edi, edi
0x18011e931  mov     rax, gs:60h
0x18011e93a  mov     r15, [rax+20h]
0x18011e93e  test    r15, r15
0x18011e941  jz      short loc_18011E949
0x18011e943  mov     r15, [r15+78h]
0x18011e947  jmp     short loc_18011E950
0x18011e949  lea     r15, aUnknown_0; "<unknown>"
0x18011e950  mov     [rsp+78h+var_48], r15
0x18011e955  call    RtlIsAnyDebuggerPresent
0x18011e95a  test    al, al
0x18011e95c  jz      loc_18011ECA3
0x18011e962  mov     r12, [rcx]
0x18011e965  cmp     dword ptr [r12], 0C0000005h
0x18011e96d  jz      loc_18011EBB4
0x18011e973  cmp     dword ptr [r12], 0C0000006h
0x18011e97b  jz      loc_18011EB15
0x18011e981  cmp     dword ptr [r12], 0C0000194h
0x18011e989  jz      short loc_18011E9FF
0x18011e98b  mov     ebx, 65h ; 'e'
0x18011e990  mov     ecx, ebx
0x18011e992  cmp     dword ptr [r12], 0C0000409h
0x18011e99a  jz      short loc_18011E9BD
0x18011e99c  mov     [rsp+78h+var_50], rdx
0x18011e9a1  mov     [rsp+78h+var_58], r15
0x18011e9a6  mov     r9d, [r12]
0x18011e9aa  lea     r8, aUnhandledExcep; "\n\n *** Unhandled exception 0x%08lx, h"...
0x18011e9b1  xor     edx, edx
0x18011e9b3  call    DbgPrintEx
0x18011e9b8  jmp     loc_18011EC2F
0x18011e9bd  mov     [rsp+78h+var_58], rdx
0x18011e9c2  mov     r9, r15
0x18011e9c5  lea     r8, aAStackBufferOv; "\n\n *** A stack buffer overrun occurre"...
0x18011e9cc  xor     edx, edx
0x18011e9ce  call    DbgPrintEx
0x18011e9d3  lea     r8, aThisIsUsuallyT; "This is usually the result of a memory "...
0x18011e9da  xor     edx, edx
0x18011e9dc  mov     ecx, ebx
0x18011e9de  call    DbgPrintEx
0x18011e9e3  lea     r8, aIfThisBugEndsU; "If this bug ends up in the shipping pro"...
0x18011e9ea  xor     edx, edx
0x18011e9ec  mov     ecx, ebx
0x18011e9ee  call    DbgPrintEx
0x18011e9f3  lea     r8, aTheStackTraceS; "The stack trace should show the guilty "...
0x18011e9fa  jmp     loc_18011EC26
0x18011e9ff  mov     r12, [r12+20h]
0x18011ea04  test    r12, r12
0x18011ea07  jz      loc_18011EB0B
0x18011ea0d  mov     rax, [r12]
0x18011ea11  mov     [rsp+78h+var_40], rax
0x18011ea16  mov     esi, 1
0x18011ea1b  test    rax, rax
0x18011ea1e  jz      short loc_18011EA91
0x18011ea20  cmp     [rax], si
0x18011ea23  jnz     short loc_18011EA91
0x18011ea25  mov     [rsp+78h+var_50], rdx
0x18011ea2a  mov     [rsp+78h+var_58], r15
0x18011ea2f  mov     r9, r12
0x18011ea32  lea     r8, aResourceTimeou; "\n\n *** Resource timeout (%p) in %ws:%"...
0x18011ea39  xor     edx, edx
0x18011ea3b  lea     ebx, [rsi+64h]
0x18011ea3e  mov     ecx, ebx
0x18011ea40  call    DbgPrintEx
0x18011ea45  mov     r9d, [r12+44h]
0x18011ea4a  mov     [rsp+78h+arg_18], r9d
0x18011ea52  mov     [rsp+78h+arg_10], r9d
0x18011ea5a  mov     ecx, ebx
0x18011ea5c  test    r9d, r9d
0x18011ea5f  jns     short loc_18011EA76
0x18011ea61  mov     r9, [r12+48h]
0x18011ea66  lea     r8, aTheResourceIsO; "The resource is owned exclusively by th"...
0x18011ea6d  xor     edx, edx
0x18011ea6f  call    DbgPrintEx
0x18011ea74  jmp     short loc_18011EAE4
0x18011ea76  jle     short loc_18011EA88
0x18011ea78  lea     r8, aTheResourceIsO_0; "The resource is owned shared by %d thre"...
0x18011ea7f  xor     edx, edx
0x18011ea81  call    DbgPrintEx
0x18011ea86  jmp     short loc_18011EAE4
0x18011ea88  lea     r8, aTheResourceIsU; "The resource is unowned.  This usually "...
0x18011ea8f  jmp     short loc_18011EADD
0x18011ea91  mov     [rsp+78h+var_50], rdx
0x18011ea96  mov     [rsp+78h+var_58], r15
0x18011ea9b  mov     r9, r12
0x18011ea9e  lea     r8, aCriticalSectio_1; "\n\n *** Critical Section Timeout (%p) "...
0x18011eaa5  xor     edx, edx
0x18011eaa7  lea     ebx, [rdx+65h]
0x18011eaaa  mov     ecx, ebx
0x18011eaac  call    DbgPrintEx
0x18011eab1  mov     r9, [r12+10h]
0x18011eab6  mov     ecx, ebx
0x18011eab8  test    r9, r9
0x18011eabb  jz      short loc_18011EAD6
0x18011eabd  lea     r8, aTheCriticalSec; "The critical section is owned by thread"...
0x18011eac4  xor     edx, edx
0x18011eac6  call    DbgPrintEx
0x18011eacb  lea     r8, aGoDetermineWhy; "Go determine why that thread has not re"...
0x18011ead2  mov     ecx, ebx
0x18011ead4  jmp     short loc_18011EADD
0x18011ead6  lea     r8, aTheCriticalSec_0; "The critical section is unowned.  This "...
0x18011eadd  xor     edx, edx
0x18011eadf  call    DbgPrintEx
0x18011eae4  jmp     loc_18011EC34
0x18011eae9  xor     edi, edi
0x18011eaeb  lea     ebx, [rdi+65h]
0x18011eaee  lea     esi, [rdi+1]
0x18011eaf1  mov     r13, [rsp+78h+arg_8]
0x18011eaf9  mov     r14, [rsp+78h+arg_0]
0x18011eb01  mov     r15, [rsp+78h+var_48]
0x18011eb06  jmp     loc_18011EC34
0x18011eb0b  mov     ebx, 65h ; 'e'
0x18011eb10  jmp     loc_18011EC2F
0x18011eb15  mov     [rsp+78h+var_58], rdx
0x18011eb1a  mov     r9, r15
0x18011eb1d  lea     r8, aInpageErrorInW; "\n\n *** Inpage error in %ws:%s\n\n"
0x18011eb24  xor     edx, edx
0x18011eb26  lea     ebx, [rdx+65h]
0x18011eb29  mov     ecx, ebx
0x18011eb2b  call    DbgPrintEx
0x18011eb30  mov     r9, [r14]
0x18011eb33  mov     rax, [r9+28h]
0x18011eb37  mov     [rsp+78h+var_58], rax
0x18011eb3c  mov     r9, [r9+10h]
0x18011eb40  lea     r8, aTheInstruction; "The instruction at %p referenced memory"...
0x18011eb47  xor     edx, edx
0x18011eb49  mov     ecx, ebx
0x18011eb4b  call    DbgPrintEx
0x18011eb50  mov     r9, [r14]
0x18011eb53  mov     r9, [r9+30h]
0x18011eb57  lea     r8, aThisFailedBeca; "This failed because of error %Ix.\n\n"
0x18011eb5e  xor     edx, edx
0x18011eb60  mov     ecx, ebx
0x18011eb62  call    DbgPrintEx
0x18011eb67  mov     rax, [r14]
0x18011eb6a  mov     rcx, [rax+30h]
0x18011eb6e  cmp     rcx, 0FFFFFFFFC000009Ah
0x18011eb75  jz      short loc_18011EBAB
0x18011eb77  cmp     rcx, 0FFFFFFFFC000009Ch
0x18011eb7e  jz      short loc_18011EBA2
0x18011eb80  cmp     rcx, 0FFFFFFFFC000016Ah
0x18011eb87  jz      short loc_18011EBA2
0x18011eb89  cmp     rcx, 0FFFFFFFFC0000185h
0x18011eb90  jnz     loc_18011EC2F
0x18011eb96  lea     r8, aThisMeansThatT; "This means that the I/O device reported"...
0x18011eb9d  jmp     loc_18011EC26
0x18011eba2  lea     r8, aThisMeansTheDa; "This means the data could not be read, "...
0x18011eba9  jmp     short loc_18011EC26
0x18011ebab  lea     r8, aThisMeansTheMa; "This means the machine is out of memory"...
0x18011ebb2  jmp     short loc_18011EC26
0x18011ebb4  mov     [rsp+78h+var_58], rdx
0x18011ebb9  mov     r9, r15
0x18011ebbc  lea     r8, aAnAccessViolat; "\n\n *** An Access Violation occurred i"...
0x18011ebc3  xor     edx, edx
0x18011ebc5  lea     ebx, [rdx+65h]
0x18011ebc8  mov     ecx, ebx
0x18011ebca  call    DbgPrintEx
0x18011ebcf  mov     r9, [r14]
0x18011ebd2  lea     rcx, aReadFrom; "read from"
0x18011ebd9  lea     rax, aWriteTo; "write to"
0x18011ebe0  cmp     [r9+20h], rdi
0x18011ebe4  cmovz   rax, rcx
0x18011ebe8  mov     [rsp+78h+var_58], rax
0x18011ebed  mov     r9, [r9+10h]
0x18011ebf1  lea     r8, aTheInstruction_0; "The instruction at %p tried to %s "
0x18011ebf8  xor     edx, edx
0x18011ebfa  mov     ecx, ebx
0x18011ebfc  call    DbgPrintEx
0x18011ec01  mov     rax, [r14]
0x18011ec04  mov     r9, [rax+28h]
0x18011ec08  test    r9, r9
0x18011ec0b  jz      short loc_18011EC1F
0x18011ec0d  lea     r8, aAnInvalidAddre; "an invalid address, %p\n\n"
0x18011ec14  xor     edx, edx
0x18011ec16  mov     ecx, ebx
0x18011ec18  call    DbgPrintEx
0x18011ec1d  jmp     short loc_18011EC2F
0x18011ec1f  lea     r8, aANullPointer; "a NULL pointer\n\n"
0x18011ec26  xor     edx, edx
0x18011ec28  mov     ecx, ebx
0x18011ec2a  call    DbgPrintEx
0x18011ec2f  mov     esi, 1
0x18011ec34  mov     r9, [r14]
0x18011ec37  lea     r8, aEnterExrPForTh; " *** enter .exr %p for the exception re"...
0x18011ec3e  xor     edx, edx
0x18011ec40  mov     ecx, ebx
0x18011ec42  call    DbgPrintEx
0x18011ec47  mov     rax, [r14]
0x18011ec4a  cmp     dword ptr [rax], 0C0000409h
0x18011ec50  jz      short loc_18011EC66
0x18011ec52  mov     r9, [r14+8]
0x18011ec56  lea     r8, aEnterCxrPForTh; " ***  enter .cxr %p for the context\n"
0x18011ec5d  xor     edx, edx
0x18011ec5f  mov     ecx, ebx
0x18011ec61  call    DbgPrintEx
0x18011ec66  lea     r8, aThenKbToGetThe; " *** then kb to get the faulting stack"...
0x18011ec6d  xor     edx, edx
0x18011ec6f  mov     ecx, ebx
0x18011ec71  call    DbgPrintEx
0x18011ec76  int     3; Trap to Debugger
0x18011ec77  mov     r9, [r14]
0x18011ec7a  cmp     dword ptr [r9], 0C0000194h
0x18011ec81  jnz     short loc_18011ECA8
0x18011ec83  mov     [rsp+78h+var_50], r13
0x18011ec88  mov     [rsp+78h+var_58], r15
0x18011ec8d  mov     r9, [r9+20h]
0x18011ec91  lea     r8, aRestartingWait; " *** Restarting wait on critsec or reso"...
0x18011ec98  xor     edx, edx
0x18011ec9a  mov     ecx, ebx
0x18011ec9c  call    DbgPrintEx
0x18011eca1  jmp     short loc_18011ECA8
0x18011eca3  mov     esi, 1
0x18011eca8  mov     rcx, [r14]
0x18011ecab  cmp     dword ptr [rcx], 0C0000409h
0x18011ecb1  jnz     short loc_18011ECBF
0x18011ecb3  xor     r8d, r8d
0x18011ecb6  mov     rdx, [r14+8]
0x18011ecba  call    RtlReportException
0x18011ecbf  mov     rcx, [r14]
0x18011ecc2  cmp     dword ptr [rcx], 0C0000194h
0x18011ecc8  setnz   dil
0x18011eccc  sub     edi, esi
0x18011ecce  mov     eax, edi
0x18011ecd0  add     rsp, 40h
0x18011ecd4  pop     r15
0x18011ecd6  pop     r14
0x18011ecd8  pop     r13
0x18011ecda  pop     r12
0x18011ecdc  pop     rdi
0x18011ecdd  pop     rsi
0x18011ecde  pop     rbx
0x18011ecdf  retn
```
