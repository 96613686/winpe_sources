# NbtDispatchCleanup

- ea: `0x14004d120`
- end: `0x14004d22b`
- name: `NbtDispatchCleanup`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006900`
- `0x14000dc40`
- `0x1400148a0`
- `0x14003005c`
- `0x1400401c4`
- `0x14004d120`
- `0x14004d234`
- `0x14004d2e4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004d1b8`
- `ntoskrnl!IofCompleteRequest` at `0x14004d1b8`

## pseudocode

```c
__int64 __fastcall NbtDispatchCleanup(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int FsContext2_low; // ecx
  int v6; // ecx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned __int8)NBT_REFERENCE_DEVICE(a1, 0, 0) )
  {
    FsContext2_low = LOWORD(CurrentStackLocation->FileObject->FsContext2);
    if ( FsContext2_low != 3 )
    {
      v6 = FsContext2_low - 1;
      if ( v6 )
      {
        v7 = (unsigned int)(v6 - 1);
        if ( (_DWORD)v7 )
        {
          if ( (_DWORD)v7 != 2 )
            goto LABEL_7;
          v8 = NTCleanUpWinsAddr(v7, a2);
        }
        else
        {
          v8 = NTCleanUpConnection(a1, a2);
        }
      }
      else
      {
        v8 = NTCleanUpAddress(a1, a2);
      }
      v9 = v8;
      if ( v8 != 259 )
      {
LABEL_8:
        ReturnIrp(a2);
        NBT_DEREFERENCE_DEVICE(a1, 0);
        return v9;
      }
    }
LABEL_7:
    v9 = 0;
    goto LABEL_8;
  }
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_qqq(
      1026,
      17,
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
0x14004d120  mov     [rsp+arg_0], rbx
0x14004d125  mov     [rsp+arg_8], rsi
0x14004d12a  push    rdi
0x14004d12b  sub     rsp, 30h
0x14004d12f  mov     rbx, [rdx+0B8h]
0x14004d136  mov     rdi, rdx
0x14004d139  xor     edx, edx
0x14004d13b  xor     r8d, r8d
0x14004d13e  mov     rsi, rcx
0x14004d141  call    NBT_REFERENCE_DEVICE
0x14004d146  test    al, al
0x14004d148  jz      short loc_14004D1A5
0x14004d14a  mov     rax, [rbx+30h]
0x14004d14e  movzx   ecx, word ptr [rax+20h]
0x14004d152  cmp     ecx, 3
0x14004d155  jz      short loc_14004D179
0x14004d157  sub     ecx, 1
0x14004d15a  jz      short loc_14004D1D7
0x14004d15c  sub     ecx, 1
0x14004d15f  jnz     loc_14004D215
0x14004d165  mov     rdx, rdi
0x14004d168  mov     rcx, rsi
0x14004d16b  call    NTCleanUpConnection
0x14004d170  mov     ebx, eax
0x14004d172  cmp     eax, 103h
0x14004d177  jnz     short loc_14004D17B
0x14004d179  xor     ebx, ebx
0x14004d17b  mov     edx, ebx
0x14004d17d  mov     rcx, rdi; Irp
0x14004d180  call    ReturnIrp
0x14004d185  xor     r8d, r8d
0x14004d188  xor     edx, edx
0x14004d18a  mov     rcx, rsi
0x14004d18d  call    NBT_DEREFERENCE_DEVICE
0x14004d192  mov     eax, ebx
0x14004d194  mov     rbx, [rsp+38h+arg_0]
0x14004d199  mov     rsi, [rsp+38h+arg_8]
0x14004d19e  add     rsp, 30h
0x14004d1a2  pop     rdi
0x14004d1a3  retn
0x14004d1a5  test    byte ptr cs:xmmword_140038420, 4
0x14004d1ac  jnz     short loc_14004D1E4
0x14004d1ae  xor     ebx, ebx
0x14004d1b0  mov     dl, 2; PriorityBoost
0x14004d1b2  mov     rcx, rdi; Irp
0x14004d1b5  mov     [rdi+30h], ebx
0x14004d1b8  call    cs:__imp_IofCompleteRequest
0x14004d1bf  nop     dword ptr [rax+rax+00h]
0x14004d1c4  mov     rbx, [rsp+38h+arg_0]
0x14004d1c9  xor     eax, eax
0x14004d1cb  mov     rsi, [rsp+38h+arg_8]
0x14004d1d0  add     rsp, 30h
0x14004d1d4  pop     rdi
0x14004d1d5  retn
0x14004d1d7  mov     rdx, rdi
0x14004d1da  mov     rcx, rsi
0x14004d1dd  call    NTCleanUpAddress
0x14004d1e2  jmp     short loc_14004D170
0x14004d1e4  mov     r8, [rbx+30h]
0x14004d1e8  mov     edx, 11h
0x14004d1ed  mov     ecx, 402h
0x14004d1f2  mov     r9, rsi
0x14004d1f5  mov     rax, [r8+20h]
0x14004d1f9  mov     [rsp+38h+var_10], rax
0x14004d1fe  mov     rax, [r8+18h]
0x14004d202  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14004d209  mov     [rsp+38h+var_18], rax
0x14004d20e  call    WPP_SF_qqq
0x14004d213  jmp     short loc_14004D1AE
0x14004d215  cmp     ecx, 2
0x14004d218  jnz     loc_14004D179
0x14004d21e  mov     rdx, rdi
0x14004d221  call    NTCleanUpWinsAddr
0x14004d226  jmp     loc_14004D170
```
