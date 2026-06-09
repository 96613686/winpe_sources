# FileSeekRoutine

- ea: `0x180148060`
- end: `0x180148105`
- name: `FileSeekRoutine`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180148060`
- `0x18015c080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18014809c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18014809c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801480ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801480ac`

## pseudocode

```c
__int64 __fastcall FileSeekRoutine(void *a1, LARGE_INTEGER a2, int a3, union _LARGE_INTEGER *a4)
{
  DWORD v5; // r9d
  signed int LastError; // eax
  unsigned int v7; // r10d
  __int64 v8; // rdx
  unsigned int v9; // r10d
  union _LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( !a1 )
    goto LABEL_15;
  if ( !a3 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  v5 = 1;
  if ( a3 != 1 )
  {
    v5 = 2;
    if ( a3 != 2 )
    {
LABEL_15:
      v8 = 2147942487LL;
      goto LABEL_16;
    }
  }
LABEL_6:
  if ( !SetFilePointerEx(a1, a2, &NewFilePointer, v5) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  if ( a4 )
  {
    if ( NewFilePointer.QuadPart < 0 )
    {
      v7 = -2147418113;
LABEL_9:
      v8 = v7;
LABEL_16:
      LogErrorFxn(a1, v8);
      return v9;
    }
    *a4 = NewFilePointer;
  }
  return 0;
}

```

## disassembly

```asm
0x180148060  push    rbx
0x180148062  sub     rsp, 30h
0x180148066  mov     qword ptr [rsp+38h+NewFilePointer], 0
0x18014806f  mov     rbx, r9
0x180148072  test    rcx, rcx
0x180148075  jz      short loc_1801480EE
0x180148077  test    r8d, r8d
0x18014807a  jnz     short loc_180148081
0x18014807c  xor     r9d, r9d
0x18014807f  jmp     short loc_180148097
0x180148081  mov     r9d, 1
0x180148087  cmp     r8d, r9d
0x18014808a  jz      short loc_180148097
0x18014808c  mov     r9d, 2; dwMoveMethod
0x180148092  cmp     r8d, r9d
0x180148095  jnz     short loc_1801480EE
0x180148097  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18014809c  call    cs:__imp_SetFilePointerEx
0x1801480a3  nop     dword ptr [rax+rax+00h]
0x1801480a8  test    eax, eax
0x1801480aa  jnz     short loc_1801480CF
0x1801480ac  call    cs:__imp_GetLastError
0x1801480b3  nop     dword ptr [rax+rax+00h]
0x1801480b8  mov     r10d, eax
0x1801480bb  test    eax, eax
0x1801480bd  jle     short loc_1801480CA
0x1801480bf  movzx   r10d, ax
0x1801480c3  or      r10d, 80070000h
0x1801480ca  mov     edx, r10d
0x1801480cd  jmp     short loc_1801480F6
0x1801480cf  test    rbx, rbx
0x1801480d2  jz      short loc_1801480E9
0x1801480d4  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x1801480d9  test    rax, rax
0x1801480dc  jns     short loc_1801480E6
0x1801480de  mov     r10d, 8000FFFFh
0x1801480e4  jmp     short loc_1801480CA
0x1801480e6  mov     [rbx], rax
0x1801480e9  xor     r10d, r10d
0x1801480ec  jmp     short loc_1801480FB
0x1801480ee  mov     edx, 80070057h
0x1801480f3  mov     r10d, edx
0x1801480f6  call    LogErrorFxn
0x1801480fb  mov     eax, r10d
0x1801480fe  add     rsp, 30h
0x180148102  pop     rbx
0x180148103  retn
```
