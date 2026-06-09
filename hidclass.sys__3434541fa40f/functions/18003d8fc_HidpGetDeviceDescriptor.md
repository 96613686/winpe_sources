# HidpGetDeviceDescriptor

- ea: `0x18003d8fc`
- end: `0x18003da15`
- name: `HidpGetDeviceDescriptor`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003d250`

## callees

- `0x180008650`
- `0x18001fba0`
- `0x180037008`
- `0x18003d8fc`
- `0x18003de60`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x18003d9db`
- `ntoskrnl!IoFreeIrp` at `0x18003d9db`
- `ntoskrnl!IoAllocateIrp` at `0x18003d916`
- `ntoskrnl!IoAllocateIrp` at `0x18003d916`

## string_xrefs

- `0x18003d9ec`: `Returned non-report descriptor`

## pseudocode

```c
__int64 __fastcall HidpGetDeviceDescriptor(_QWORD *a1)
{
  PIRP Irp; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  IRP *v5; // rsi
  unsigned int HidReportDescriptor; // ebx
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  _IO_STACK_LOCATION *v11; // rcx
  _QWORD *v12; // rcx
  const char *v13; // r8
  __int64 v14; // rdx

  Irp = IoAllocateIrp(*(_BYTE *)(*a1 + 76LL), 0);
  v5 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 720899;
    Irp->UserBuffer = (char *)a1 + 92;
    CurrentStackLocation[-1].Parameters.Read.Length = 9;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    if ( !(unsigned int)HidpCallDriverSynchronous(*a1, Irp, v4) )
    {
      if ( v5->IoStatus.Information != 9 )
      {
        v13 = "Returned size invalid";
        v14 = 720899;
        v12 = a1;
        goto LABEL_12;
      }
      v11 = v5->Tail.Overlay.CurrentStackLocation;
      v11[-1].Parameters.Read.ByteOffset.LowPart = 720935;
      v5->UserBuffer = a1 + 13;
      v11[-1].Parameters.Read.Length = 32;
      if ( (int)HidpCallDriverSynchronous(*a1, v5, v9) >= 0 )
      {
        v12 = a1;
        if ( *((_BYTE *)a1 + 98) == 34 )
        {
          HidReportDescriptor = GetHidReportDescriptor(a1, v5, *(unsigned __int16 *)((char *)a1 + 99));
LABEL_10:
          IoFreeIrp(v5);
          return HidReportDescriptor;
        }
        v13 = "Returned non-report descriptor";
        v14 = 720935;
LABEL_12:
        HidReportDescriptor = -1073741668;
        TraceLoggingIrpIoctlFailed(v12, v14, v13, v10);
        goto LABEL_10;
      }
    }
    HidReportDescriptor = -1073741668;
    goto LABEL_10;
  }
  HidReportDescriptor = -1073741670;
  TraceLoggingIoAllocateIrpFailed((unsigned int)*(char *)(*a1 + 76LL), v3, v4);
  return HidReportDescriptor;
}

```

## disassembly

```asm
0x18003d8fc  mov     [rsp+arg_0], rbx
0x18003d901  mov     [rsp+arg_8], rsi
0x18003d906  push    rdi
0x18003d907  sub     rsp, 20h
0x18003d90b  mov     rdi, rcx
0x18003d90e  xor     edx, edx; ChargeQuota
0x18003d910  mov     rcx, [rcx]
0x18003d913  mov     cl, [rcx+4Ch]; StackSize
0x18003d916  call    cs:__imp_IoAllocateIrp
0x18003d91d  nop     dword ptr [rax+rax+00h]
0x18003d922  mov     rsi, rax
0x18003d925  test    rax, rax
0x18003d928  jnz     short loc_18003D94E
0x18003d92a  mov     rax, [rdi]
0x18003d92d  mov     ebx, 0C000009Ah
0x18003d932  movsx   ecx, byte ptr [rax+4Ch]
0x18003d936  call    TraceLoggingIoAllocateIrpFailed
0x18003d93b  mov     rsi, [rsp+28h+arg_8]
0x18003d940  mov     eax, ebx
0x18003d942  mov     rbx, [rsp+28h+arg_0]
0x18003d947  add     rsp, 20h
0x18003d94b  pop     rdi
0x18003d94c  retn
0x18003d94e  mov     rdx, [rax+0B8h]
0x18003d955  lea     rbx, [rdi+5Ch]
0x18003d959  mov     byte ptr [rdx-48h], 0Fh
0x18003d95d  mov     dword ptr [rdx-30h], 0B0003h
0x18003d964  mov     [rax+70h], rbx
0x18003d968  mov     dword ptr [rdx-40h], 9
0x18003d96f  mov     qword ptr [rdx-28h], 0
0x18003d977  mov     rdx, rsi
0x18003d97a  mov     rcx, [rdi]
0x18003d97d  call    HidpCallDriverSynchronous
0x18003d982  test    eax, eax
0x18003d984  jnz     short loc_18003D9D3
0x18003d986  cmp     qword ptr [rsi+38h], 9
0x18003d98b  jnz     short loc_18003DA04
0x18003d98d  mov     rcx, [rsi+0B8h]
0x18003d994  lea     rax, [rdi+68h]
0x18003d998  mov     rdx, rsi
0x18003d99b  mov     dword ptr [rcx-30h], 0B0027h
0x18003d9a2  mov     [rsi+70h], rax
0x18003d9a6  mov     dword ptr [rcx-40h], 20h ; ' '
0x18003d9ad  mov     rcx, [rdi]
0x18003d9b0  call    HidpCallDriverSynchronous
0x18003d9b5  test    eax, eax
0x18003d9b7  js      short loc_18003D9D3
0x18003d9b9  cmp     byte ptr [rbx+6], 22h ; '"'
0x18003d9bd  mov     rcx, rdi
0x18003d9c0  jnz     short loc_18003D9EC
0x18003d9c2  movzx   r8d, word ptr [rbx+7]
0x18003d9c7  mov     rdx, rsi
0x18003d9ca  call    GetHidReportDescriptor
0x18003d9cf  mov     ebx, eax
0x18003d9d1  jmp     short loc_18003D9D8
0x18003d9d3  mov     ebx, 0C000009Ch
0x18003d9d8  mov     rcx, rsi; Irp
0x18003d9db  call    cs:__imp_IoFreeIrp
0x18003d9e2  nop     dword ptr [rax+rax+00h]
0x18003d9e7  jmp     loc_18003D93B
0x18003d9ec  lea     r8, aReturnedNonRep; "Returned non-report descriptor"
0x18003d9f3  mov     edx, 0B0027h
0x18003d9f8  mov     ebx, 0C000009Ch
0x18003d9fd  call    TraceLoggingIrpIoctlFailed
0x18003da02  jmp     short loc_18003D9D8
0x18003da04  lea     r8, aReturnedSizeIn; "Returned size invalid"
0x18003da0b  mov     edx, 0B0003h
0x18003da10  mov     rcx, rdi
0x18003da13  jmp     short loc_18003D9F8
```
