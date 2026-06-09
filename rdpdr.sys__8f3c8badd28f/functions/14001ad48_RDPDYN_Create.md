# RDPDYN_Create

- ea: `0x14001ad48`
- end: `0x14001ae18`
- name: `RDPDYN_Create`
- size: `208`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002b930`

## callees

- `0x14001ad48`
- `0x14001af78`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001adf9`
- `ntoskrnl!IofCompleteRequest` at `0x14001adf9`

## pseudocode

```c
__int64 __fastcall RDPDYN_Create(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  PFILE_OBJECT FileObject; // rbx
  unsigned int Length; // eax
  __int64 v6; // r10
  unsigned int v7; // r8d
  bool v8; // zf
  unsigned int v9; // ebx
  __int128 v11; // [rsp+20h] [rbp-28h]
  wchar_t v12; // [rsp+30h] [rbp-18h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12 = aSession[8];
  FileObject = CurrentStackLocation->FileObject;
  v11 = *(_OWORD *)L"\\session";
  Length = FileObject->FileName.Length;
  if ( (_WORD)Length )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)&v11 + v6) );
    v7 = 0;
    if ( Length >> 1 )
    {
      while ( 1 )
      {
        v8 = v7 == (_DWORD)v6;
        if ( v7 >= (unsigned int)v6 )
          break;
        if ( FileObject->FileName.Buffer[v7] != *((_WORD *)&v11 + v7) )
          goto LABEL_11;
        if ( ++v7 >= Length >> 1 )
          goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      v8 = v7 == (_DWORD)v6;
    }
    if ( v8 )
      v9 = RDPDYN_PrepareForDevMgmt(FileObject, &FileObject->FileName.Buffer[(unsigned int)v6], a2);
    else
LABEL_11:
      v9 = 0;
  }
  else
  {
    v9 = -1073741823;
  }
  a2->IoStatus.Status = v9;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v9;
}

```

## disassembly

```asm
0x14001ad48  mov     [rsp+arg_0], rbx
0x14001ad4d  mov     [rsp+arg_8], rsi
0x14001ad52  push    rdi
0x14001ad53  sub     rsp, 40h
0x14001ad57  movzx   eax, word ptr cs:aSession+10h; ""
0x14001ad5e  xor     esi, esi
0x14001ad60  mov     r9, [rdx+0B8h]
0x14001ad67  mov     rdi, rdx
0x14001ad6a  movups  xmm0, xmmword ptr cs:aSession; "\\session"
0x14001ad71  mov     [rsp+48h+var_18], ax
0x14001ad76  mov     rbx, [r9+30h]
0x14001ad7a  movups  [rsp+48h+var_28], xmm0
0x14001ad7f  movzx   eax, word ptr [rbx+58h]
0x14001ad83  test    ax, ax
0x14001ad86  jz      short loc_14001ADE8
0x14001ad88  lea     rcx, [rsp+48h+var_28]
0x14001ad8d  or      r10, 0FFFFFFFFFFFFFFFFh
0x14001ad91  inc     r10
0x14001ad94  cmp     [rcx+r10*2], si
0x14001ad99  jnz     short loc_14001AD91
0x14001ad9b  mov     r11d, eax
0x14001ad9e  mov     r8d, esi
0x14001ada1  shr     r11d, 1
0x14001ada4  jz      short loc_14001ADC5
0x14001ada6  cmp     r8d, r10d
0x14001ada9  jnb     short loc_14001ADC8
0x14001adab  mov     rcx, [rbx+60h]
0x14001adaf  mov     edx, r8d
0x14001adb2  movzx   eax, word ptr [rsp+rdx*2+48h+var_28]
0x14001adb7  cmp     [rcx+rdx*2], ax
0x14001adbb  jnz     short loc_14001ADE4
0x14001adbd  inc     r8d
0x14001adc0  cmp     r8d, r11d
0x14001adc3  jb      short loc_14001ADA6
0x14001adc5  cmp     r8d, r10d
0x14001adc8  jnz     short loc_14001ADE4
0x14001adca  mov     rax, [rbx+60h]
0x14001adce  mov     r8, rdi
0x14001add1  mov     edx, r10d
0x14001add4  mov     rcx, rbx
0x14001add7  lea     rdx, [rax+rdx*2]
0x14001addb  call    RDPDYN_PrepareForDevMgmt
0x14001ade0  mov     ebx, eax
0x14001ade2  jmp     short loc_14001ADED
0x14001ade4  mov     ebx, esi
0x14001ade6  jmp     short loc_14001ADED
0x14001ade8  mov     ebx, 0C0000001h
0x14001aded  xor     edx, edx; PriorityBoost
0x14001adef  mov     [rdi+30h], ebx
0x14001adf2  mov     rcx, rdi; Irp
0x14001adf5  mov     [rdi+38h], rsi
0x14001adf9  call    cs:__imp_IofCompleteRequest
0x14001ae00  nop     dword ptr [rax+rax+00h]
0x14001ae05  mov     rsi, [rsp+48h+arg_8]
0x14001ae0a  mov     eax, ebx
0x14001ae0c  mov     rbx, [rsp+48h+arg_0]
0x14001ae11  add     rsp, 40h
0x14001ae15  pop     rdi
0x14001ae16  retn
```
