# NbtDispatchClose

- ea: `0x14004ce30`
- end: `0x14004cf54`
- name: `NbtDispatchClose`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006900`
- `0x14000dc40`
- `0x1400148a0`
- `0x1400401c4`
- `0x14004025c`
- `0x14004ce30`
- `0x14004cf5c`
- `0x14004d028`
- `0x140052010`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004cea0`
- `ntoskrnl!IofCompleteRequest` at `0x14004cea0`

## pseudocode

```c
__int64 __fastcall NbtDispatchClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v5; // rcx
  unsigned int v6; // ebx
  PFILE_OBJECT FileObject; // r9
  int FsContext2; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned __int8)NBT_REFERENCE_DEVICE(a1, 0, 0) )
  {
    v6 = 0;
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 0;
    FileObject = CurrentStackLocation->FileObject;
    FsContext2 = (int)FileObject->FsContext2;
    if ( FsContext2 == 3 )
    {
LABEL_3:
      ReturnIrp(a2);
LABEL_4:
      NBT_DEREFERENCE_DEVICE(a1, 0);
      return v6;
    }
    v10 = FsContext2 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 2 )
        {
          if ( (xmmword_140038420 & 4) != 0 )
            WPP_SF_q(1026, 19, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, FileObject->FsContext2);
          goto LABEL_3;
        }
        v12 = NTCloseWinsAddr(a1, a2);
      }
      else
      {
        v12 = NTCloseConnection(v5, a2);
      }
    }
    else
    {
      v12 = NTCloseAddress(v5, a2);
    }
    v6 = v12;
    if ( v12 == 259 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_qqq(
      1026,
      18,
      WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids,
      a1,
      CurrentStackLocation->FileObject->FsContext,
      CurrentStackLocation->FileObject->FsContext2);
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 2);
  return 0;
}

```

## disassembly

```asm
0x14004ce30  push    rbx
0x14004ce32  push    rbp
0x14004ce33  push    rsi
0x14004ce34  push    rdi
0x14004ce35  sub     rsp, 38h
0x14004ce39  mov     rbp, [rdx+0B8h]
0x14004ce40  mov     rdi, rdx
0x14004ce43  xor     edx, edx
0x14004ce45  xor     r8d, r8d
0x14004ce48  mov     rsi, rcx
0x14004ce4b  call    NBT_REFERENCE_DEVICE
0x14004ce50  test    al, al
0x14004ce52  jz      short loc_14004CE8D
0x14004ce54  xor     ebx, ebx
0x14004ce56  mov     [rdi+30h], ebx
0x14004ce59  mov     [rdi+38h], rbx
0x14004ce5d  mov     r9, [rbp+30h]
0x14004ce61  mov     eax, [r9+20h]
0x14004ce65  cmp     eax, 3
0x14004ce68  jnz     short loc_14004CEB8
0x14004ce6a  mov     edx, ebx
0x14004ce6c  mov     rcx, rdi; Irp
0x14004ce6f  call    ReturnIrp
0x14004ce74  xor     r8d, r8d
0x14004ce77  xor     edx, edx
0x14004ce79  mov     rcx, rsi
0x14004ce7c  call    NBT_DEREFERENCE_DEVICE
0x14004ce81  mov     eax, ebx
0x14004ce83  add     rsp, 38h
0x14004ce87  pop     rdi
0x14004ce88  pop     rsi
0x14004ce89  pop     rbp
0x14004ce8a  pop     rbx
0x14004ce8b  retn
0x14004ce8d  test    byte ptr cs:xmmword_140038420, 4
0x14004ce94  jnz     short loc_14004CF10
0x14004ce96  xor     ebx, ebx
0x14004ce98  mov     dl, 2; PriorityBoost
0x14004ce9a  mov     rcx, rdi; Irp
0x14004ce9d  mov     [rdi+30h], ebx
0x14004cea0  call    cs:__imp_IofCompleteRequest
0x14004cea7  nop     dword ptr [rax+rax+00h]
0x14004ceac  xor     eax, eax
0x14004ceae  add     rsp, 38h
0x14004ceb2  pop     rdi
0x14004ceb3  pop     rsi
0x14004ceb4  pop     rbp
0x14004ceb5  pop     rbx
0x14004ceb6  retn
0x14004ceb8  sub     eax, 1
0x14004cebb  jz      short loc_14004CED5
0x14004cebd  sub     eax, 1
0x14004cec0  jnz     short loc_14004CEDF
0x14004cec2  mov     rdx, rdi
0x14004cec5  call    NTCloseConnection
0x14004ceca  mov     ebx, eax
0x14004cecc  cmp     eax, 103h
0x14004ced1  jz      short loc_14004CE74
0x14004ced3  jmp     short loc_14004CE6A
0x14004ced5  mov     rdx, rdi
0x14004ced8  call    NTCloseAddress
0x14004cedd  jmp     short loc_14004CECA
0x14004cedf  cmp     eax, 2
0x14004cee2  jz      short loc_14004CF44
0x14004cee4  test    byte ptr cs:xmmword_140038420, 4
0x14004ceeb  jz      loc_14004CE6A
0x14004cef1  mov     r9, [r9+20h]
0x14004cef5  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14004cefc  mov     edx, 13h
0x14004cf01  mov     ecx, 402h
0x14004cf06  call    WPP_SF_q
0x14004cf0b  jmp     loc_14004CE6A
0x14004cf10  mov     r8, [rbp+30h]
0x14004cf14  mov     edx, 12h
0x14004cf19  mov     ecx, 402h
0x14004cf1e  mov     r9, rsi
0x14004cf21  mov     rax, [r8+20h]
0x14004cf25  mov     [rsp+58h+var_30], rax
0x14004cf2a  mov     rax, [r8+18h]
0x14004cf2e  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14004cf35  mov     [rsp+58h+var_38], rax
0x14004cf3a  call    WPP_SF_qqq
0x14004cf3f  jmp     loc_14004CE96
0x14004cf44  mov     rdx, rdi
0x14004cf47  mov     rcx, rsi
0x14004cf4a  call    NTCloseWinsAddr
0x14004cf4f  jmp     loc_14004CECA
```
