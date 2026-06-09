# ProvDeviceControl

- ea: `0x14000a050`
- end: `0x14000a0f3`
- name: `ProvDeviceControl`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a050`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a0d4`
- `ntoskrnl!IofCompleteRequest` at `0x14000a0d4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0ab`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0ab`

## pseudocode

```c
__int64 __fastcall ProvDeviceControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v3; // ebx
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  _QWORD *UserBuffer; // rsi

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  a2->IoStatus.Information = 0;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( !Parameters )
    goto LABEL_9;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x28 )
    goto LABEL_9;
  UserBuffer = a2->UserBuffer;
  if ( !UserBuffer || CurrentStackLocation->Parameters.Read.Length < 8 )
    goto LABEL_9;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2228231 )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&Parameters->CompletionMode, &String2, 0) )
    {
      *UserBuffer = &ProvCipherFunctionTable;
      goto LABEL_10;
    }
LABEL_9:
    v3 = -1073741811;
    goto LABEL_10;
  }
  v3 = -1073741808;
LABEL_10:
  a2->IoStatus.Status = v3;
  IofCompleteRequest(a2, 0);
  return v3;
}

```

## disassembly

```asm
0x14000a050  mov     [rsp+arg_0], rbx
0x14000a055  mov     [rsp+arg_8], rsi
0x14000a05a  push    rdi
0x14000a05b  sub     rsp, 20h
0x14000a05f  mov     rax, [rdx+0B8h]
0x14000a066  xor     ebx, ebx
0x14000a068  mov     [rdx+38h], rbx
0x14000a06c  mov     rdi, rdx
0x14000a06f  mov     rcx, [rax+20h]
0x14000a073  test    rcx, rcx
0x14000a076  jz      short loc_14000A0C7
0x14000a078  cmp     dword ptr [rax+10h], 28h ; '('
0x14000a07c  jb      short loc_14000A0C7
0x14000a07e  mov     rsi, [rdx+70h]
0x14000a082  test    rsi, rsi
0x14000a085  jz      short loc_14000A0C7
0x14000a087  cmp     dword ptr [rax+8], 8
0x14000a08b  jb      short loc_14000A0C7
0x14000a08d  cmp     dword ptr [rax+18h], 220007h
0x14000a094  jz      short loc_14000A09D
0x14000a096  mov     ebx, 0C0000010h
0x14000a09b  jmp     short loc_14000A0CC
0x14000a09d  add     rcx, 8; String1
0x14000a0a1  lea     rdx, String2; String2
0x14000a0a8  xor     r8d, r8d; CaseInSensitive
0x14000a0ab  call    cs:__imp_RtlCompareUnicodeString
0x14000a0b2  nop     dword ptr [rax+rax+00h]
0x14000a0b7  test    eax, eax
0x14000a0b9  jnz     short loc_14000A0C7
0x14000a0bb  lea     rax, ProvCipherFunctionTable
0x14000a0c2  mov     [rsi], rax
0x14000a0c5  jmp     short loc_14000A0CC
0x14000a0c7  mov     ebx, 0C000000Dh
0x14000a0cc  xor     edx, edx; PriorityBoost
0x14000a0ce  mov     [rdi+30h], ebx
0x14000a0d1  mov     rcx, rdi; Irp
0x14000a0d4  call    cs:__imp_IofCompleteRequest
0x14000a0db  nop     dword ptr [rax+rax+00h]
0x14000a0e0  mov     rsi, [rsp+28h+arg_8]
0x14000a0e5  mov     eax, ebx
0x14000a0e7  mov     rbx, [rsp+28h+arg_0]
0x14000a0ec  add     rsp, 20h
0x14000a0f0  pop     rdi
0x14000a0f1  retn
```
