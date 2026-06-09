# RxLogEventWithAnnotation

- ea: `0x14001c210`
- end: `0x14001c359`
- name: `RxLogEventWithAnnotation`
- size: `329`
- prototype: `void __stdcall(PRDBSS_DEVICE_OBJECT DeviceObject, ULONG EventId, NTSTATUS Status, PVOID DataBuffer, USHORT DataBufferLength, PUNICODE_STRING Annotation, ULONG AnnotationCount)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c1b0`
- `0x14001c360`

## callees

- `0x14001c210`
- `0x140025d80`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001c29b`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001c29b`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001c33b`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001c33b`

## pseudocode

```c
void __stdcall RxLogEventWithAnnotation(
        PRDBSS_DEVICE_OBJECT DeviceObject,
        ULONG EventId,
        NTSTATUS Status,
        PVOID DataBuffer,
        USHORT DataBufferLength,
        PUNICODE_STRING Annotation,
        ULONG AnnotationCount)
{
  unsigned __int16 v7; // bx
  int v8; // r11d
  ULONG i; // r10d
  __int64 v13; // rax
  char *ErrorLogEntry; // rax
  char *v15; // rdi
  ULONG v16; // ebp
  char *j; // r14
  __int64 v18; // rbx
  char *v19; // rdx

  v7 = 0;
  v8 = 0;
  for ( i = 0; i < AnnotationCount; v8 += Annotation[v13].Length + 2 )
    v13 = i++;
  if ( DataBuffer )
    v7 = (DataBufferLength + 1) & 0xFFFE;
  if ( v8 + (unsigned int)v7 + 48 <= 0xFF )
  {
    ErrorLogEntry = (char *)IoAllocateErrorLogEntry(DeviceObject, v8 + (unsigned __int8)v7 + 48);
    v15 = ErrorLogEntry;
    if ( ErrorLogEntry )
    {
      *((_DWORD *)ErrorLogEntry + 3) = EventId;
      *(_WORD *)ErrorLogEntry = 0;
      *((_DWORD *)ErrorLogEntry + 4) = 0;
      *((_DWORD *)ErrorLogEntry + 7) = 0;
      *((_QWORD *)ErrorLogEntry + 4) = 0;
      *((_DWORD *)ErrorLogEntry + 5) = Status;
      *((_WORD *)ErrorLogEntry + 1) = DataBufferLength;
      *((_WORD *)ErrorLogEntry + 3) = v7 + 40;
      *((_WORD *)ErrorLogEntry + 2) = AnnotationCount;
      *((_DWORD *)ErrorLogEntry + 6) = 0;
      if ( DataBuffer )
        memmove(ErrorLogEntry + 40, DataBuffer, DataBufferLength);
      v16 = 0;
      for ( j = &v15[v7 + 40]; v16 < AnnotationCount; j = v19 + 2 )
      {
        v18 = v16;
        memmove(j, Annotation[v16].Buffer, Annotation[v16].Length);
        ++v16;
        v19 = &j[2 * ((unsigned __int64)Annotation[v18].Length >> 1)];
        *(_WORD *)v19 = 0;
      }
      IoWriteErrorLogEntry(v15);
    }
  }
}

```

## disassembly

```asm
0x14001c210  push    rbx
0x14001c212  push    rbp
0x14001c213  push    rsi
0x14001c214  push    rdi
0x14001c215  push    r12
0x14001c217  push    r13
0x14001c219  push    r14
0x14001c21b  push    r15
0x14001c21d  sub     rsp, 28h
0x14001c221  mov     esi, [rsp+68h+AnnotationCount]
0x14001c228  xor     ebx, ebx
0x14001c22a  mov     r15, [rsp+68h+Annotation]
0x14001c232  xor     r11d, r11d
0x14001c235  xor     r10d, r10d
0x14001c238  mov     r12d, r8d
0x14001c23b  mov     r8, rcx
0x14001c23e  mov     r14, r9
0x14001c241  lea     ecx, [rbx+1]
0x14001c244  mov     r13d, edx
0x14001c247  test    esi, esi
0x14001c249  jz      short loc_14001C265
0x14001c24b  mov     eax, r10d
0x14001c24e  add     r11d, 2
0x14001c252  add     rax, rax
0x14001c255  add     r10d, ecx
0x14001c258  movzx   eax, word ptr [r15+rax*8]
0x14001c25d  add     r11d, eax
0x14001c260  cmp     r10d, esi
0x14001c263  jb      short loc_14001C24B
0x14001c265  movzx   ebp, [rsp+68h+DataBufferLength]
0x14001c26d  test    r14, r14
0x14001c270  jz      short loc_14001C27D
0x14001c272  lea     ebx, [rcx+rbp]
0x14001c275  mov     ecx, 0FFFEh
0x14001c27a  and     bx, cx
0x14001c27d  movzx   ecx, bx
0x14001c280  add     ecx, 30h ; '0'
0x14001c283  add     ecx, r11d
0x14001c286  cmp     ecx, 0FFh
0x14001c28c  ja      loc_14001C347
0x14001c292  lea     edx, [rbx+30h]
0x14001c295  mov     rcx, r8; IoObject
0x14001c298  add     dl, r11b; EntrySize
0x14001c29b  call    cs:__imp_IoAllocateErrorLogEntry
0x14001c2a2  nop     dword ptr [rax+rax+00h]
0x14001c2a7  mov     rdi, rax
0x14001c2aa  test    rax, rax
0x14001c2ad  jz      loc_14001C347
0x14001c2b3  mov     [rax+0Ch], r13d
0x14001c2b7  xor     r13d, r13d
0x14001c2ba  mov     [rax], r13w
0x14001c2be  mov     [rax+10h], r13d
0x14001c2c2  mov     [rax+1Ch], r13d
0x14001c2c6  mov     [rax+20h], r13
0x14001c2ca  mov     [rax+14h], r12d
0x14001c2ce  mov     [rax+2], bp
0x14001c2d2  lea     eax, [rbx+28h]
0x14001c2d5  mov     [rdi+6], ax
0x14001c2d9  mov     [rdi+4], si
0x14001c2dd  mov     [rdi+18h], r13d
0x14001c2e1  test    r14, r14
0x14001c2e4  jz      short loc_14001C2F5
0x14001c2e6  mov     r8, rbp; Size
0x14001c2e9  lea     rcx, [rdi+28h]; void *
0x14001c2ed  mov     rdx, r14; Src
0x14001c2f0  call    memmove
0x14001c2f5  movzx   r14d, bx
0x14001c2f9  mov     ebp, r13d
0x14001c2fc  add     r14, 28h ; '('
0x14001c300  add     r14, rdi
0x14001c303  test    esi, esi
0x14001c305  jz      short loc_14001C338
0x14001c307  mov     ebx, ebp
0x14001c309  mov     rcx, r14; void *
0x14001c30c  add     rbx, rbx
0x14001c30f  movzx   r8d, word ptr [r15+rbx*8]; Size
0x14001c314  mov     rdx, [r15+rbx*8+8]; Src
0x14001c319  call    memmove
0x14001c31e  movzx   eax, word ptr [r15+rbx*8]
0x14001c323  inc     ebp
0x14001c325  shr     rax, 1
0x14001c328  lea     rdx, [r14+rax*2]
0x14001c32c  mov     [rdx], r13w
0x14001c330  lea     r14, [rdx+2]
0x14001c334  cmp     ebp, esi
0x14001c336  jb      short loc_14001C307
0x14001c338  mov     rcx, rdi; ElEntry
0x14001c33b  call    cs:__imp_IoWriteErrorLogEntry
0x14001c342  nop     dword ptr [rax+rax+00h]
0x14001c347  add     rsp, 28h
0x14001c34b  pop     r15
0x14001c34d  pop     r14
0x14001c34f  pop     r13
0x14001c351  pop     r12
0x14001c353  pop     rdi
0x14001c354  pop     rsi
0x14001c355  pop     rbp
0x14001c356  pop     rbx
0x14001c357  retn
```
