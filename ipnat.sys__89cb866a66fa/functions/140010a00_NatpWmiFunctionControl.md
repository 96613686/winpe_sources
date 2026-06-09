# NatpWmiFunctionControl

- ea: `0x140010a00`
- end: `0x140010c6c`
- name: `NatpWmiFunctionControl`
- size: `620`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140010a00`
- `0x140010d50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010b0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ac4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ac4`
- `WMILIB!WmiCompleteRequest` at `0x140010be5`
- `WMILIB!WmiCompleteRequest` at `0x140010be5`

## pseudocode

```c
__int64 __fastcall NatpWmiFunctionControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, unsigned int a3, int a4, char a5)
{
  __int64 v6; // rsi
  char v9; // di
  NTSTATUS v10; // ebp
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rbx
  __int64 v12; // rbx
  KIRQL v13; // al
  int v14; // edx
  int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // eax
  unsigned int v18; // ebx

  v6 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a3);
  }
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, 0);
    }
    v10 = -1073741808;
  }
  else if ( (unsigned int)v6 >= 3 )
  {
    v10 = -1073741163;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        58,
        WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    v9 = a5;
    v10 = 0;
    if ( a5 )
    {
      Parameters = Irp->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters;
      if ( Parameters->NamedPipeType < 0x38 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
        }
        v12 = 0;
        v9 = 0;
      }
      else
      {
        v12 = *(_QWORD *)&Parameters[1].CompletionMode;
      }
    }
    else
    {
      v12 = 0;
    }
    v13 = KeAcquireSpinLockRaiseToDpc(&NatWmiLock);
    *((_QWORD *)&NatWmiLogHandles + v6) = v12;
    *((_DWORD *)&NatWmiEnabledEvents + v6) = v9 != 0;
    if ( !(_DWORD)v6 )
    {
      *((_QWORD *)&NatWmiLogHandles + 1) = v12;
      HIDWORD(NatWmiEnabledEvents) = v9 != 0;
    }
    KeReleaseSpinLock(&NatWmiLock, v13);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v16 = "Enabled";
      if ( !v9 )
        v16 = "Disabled";
      WPP_SF_slI(WPP_GLOBAL_Control->AttachedDevice, v14, v15, (_DWORD)v16, v6, v12);
    }
  }
  v17 = WmiCompleteRequest(DeviceObject, Irp, v10, 0, 0);
  v18 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v18;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v17);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v18);
  }
  return v18;
}

```

## disassembly

```asm
0x140010a00  push    rbx
0x140010a02  push    rbp
0x140010a03  push    rsi
0x140010a04  push    rdi
0x140010a05  push    r13
0x140010a07  push    r14
0x140010a09  push    r15
0x140010a0b  sub     rsp, 30h
0x140010a0f  mov     ebx, r9d
0x140010a12  mov     esi, r8d
0x140010a15  mov     r14, rdx
0x140010a18  mov     r15, rcx
0x140010a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a22  lea     r13, WPP_GLOBAL_Control
0x140010a29  cmp     rcx, r13
0x140010a2c  jz      short loc_140010A53
0x140010a2e  mov     eax, [rcx+2Ch]
0x140010a31  test    al, 1
0x140010a33  jz      short loc_140010A53
0x140010a35  cmp     byte ptr [rcx+29h], 6
0x140010a39  jb      short loc_140010A53
0x140010a3b  mov     rcx, [rcx+18h]
0x140010a3f  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010a46  mov     edx, 37h ; '7'
0x140010a4b  mov     r9d, esi
0x140010a4e  call    WPP_SF_d
0x140010a53  test    ebx, ebx
0x140010a55  jnz     loc_140010B9E
0x140010a5b  cmp     esi, 3
0x140010a5e  jnb     loc_140010B66
0x140010a64  mov     dil, [rsp+68h+arg_20]
0x140010a6c  xor     ebp, ebp
0x140010a6e  test    dil, dil
0x140010a71  jz      short loc_140010ABB
0x140010a73  mov     rax, [r14+0B8h]
0x140010a7a  lea     edx, [rbp+38h]
0x140010a7d  mov     rbx, [rax+20h]
0x140010a81  cmp     [rbx], edx
0x140010a83  jb      short loc_140010A8B
0x140010a85  mov     rbx, [rbx+30h]
0x140010a89  jmp     short loc_140010ABD
0x140010a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a92  cmp     rcx, r13
0x140010a95  jz      short loc_140010AB4
0x140010a97  mov     eax, [rcx+2Ch]
0x140010a9a  test    al, 1
0x140010a9c  jz      short loc_140010AB4
0x140010a9e  cmp     byte ptr [rcx+29h], 2
0x140010aa2  jb      short loc_140010AB4
0x140010aa4  mov     rcx, [rcx+18h]
0x140010aa8  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010aaf  call    WPP_SF_
0x140010ab4  xor     ebx, ebx
0x140010ab6  xor     dil, dil
0x140010ab9  jmp     short loc_140010ABD
0x140010abb  xor     ebx, ebx
0x140010abd  lea     rcx, NatWmiLock; SpinLock
0x140010ac4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010acb  nop     dword ptr [rax+rax+00h]
0x140010ad0  xor     r8d, r8d
0x140010ad3  lea     r9, cs:140000000h
0x140010ada  test    dil, dil
0x140010add  mov     qword ptr rva NatWmiLogHandles[r9+rsi*8], rbx
0x140010ae5  setnz   r8b
0x140010ae9  mov     dword ptr rva NatWmiEnabledEvents[r9+rsi*4], r8d
0x140010af1  test    esi, esi
0x140010af3  jnz     short loc_140010B03
0x140010af5  mov     qword ptr cs:NatWmiLogHandles+8, rbx
0x140010afc  mov     dword ptr cs:NatWmiEnabledEvents+4, r8d
0x140010b03  mov     dl, al; NewIrql
0x140010b05  lea     rcx, NatWmiLock; SpinLock
0x140010b0c  call    cs:__imp_KeReleaseSpinLock
0x140010b13  nop     dword ptr [rax+rax+00h]
0x140010b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b1f  cmp     rcx, r13
0x140010b22  jz      loc_140010BD4
0x140010b28  mov     eax, [rcx+2Ch]
0x140010b2b  test    al, 1
0x140010b2d  jz      loc_140010BD4
0x140010b33  cmp     byte ptr [rcx+29h], 5
0x140010b37  jb      loc_140010BD4
0x140010b3d  mov     rcx, [rcx+18h]
0x140010b41  lea     rax, aDisabled; "Disabled"
0x140010b48  test    dil, dil
0x140010b4b  mov     [rsp+68h+var_40], rbx
0x140010b50  lea     r9, aEnabled; "Enabled"
0x140010b57  mov     dword ptr [rsp+68h+PriorityBoost], esi
0x140010b5b  cmovz   r9, rax
0x140010b5f  call    WPP_SF_slI
0x140010b64  jmp     short loc_140010BD4
0x140010b66  mov     ebp, 0C0000295h
0x140010b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b72  cmp     rcx, r13
0x140010b75  jz      short loc_140010BD4
0x140010b77  mov     eax, [rcx+2Ch]
0x140010b7a  test    al, 1
0x140010b7c  jz      short loc_140010BD4
0x140010b7e  cmp     byte ptr [rcx+29h], 2
0x140010b82  jb      short loc_140010BD4
0x140010b84  mov     rcx, [rcx+18h]
0x140010b88  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010b8f  mov     edx, 3Ah ; ':'
0x140010b94  mov     r9d, esi
0x140010b97  call    WPP_SF_d
0x140010b9c  jmp     short loc_140010BD4
0x140010b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ba5  cmp     rcx, r13
0x140010ba8  jz      short loc_140010BCF
0x140010baa  mov     eax, [rcx+2Ch]
0x140010bad  test    al, 1
0x140010baf  jz      short loc_140010BCF
0x140010bb1  cmp     byte ptr [rcx+29h], 5
0x140010bb5  jb      short loc_140010BCF
0x140010bb7  mov     rcx, [rcx+18h]
0x140010bbb  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010bc2  mov     edx, 3Bh ; ';'
0x140010bc7  xor     r9d, r9d
0x140010bca  call    WPP_SF_d
0x140010bcf  mov     ebp, 0C0000010h
0x140010bd4  xor     r9d, r9d; BufferUsed
0x140010bd7  mov     [rsp+68h+PriorityBoost], 0; PriorityBoost
0x140010bdc  mov     r8d, ebp; Status
0x140010bdf  mov     rdx, r14; Irp
0x140010be2  mov     rcx, r15; DeviceObject
0x140010be5  call    cs:__imp_WmiCompleteRequest
0x140010bec  nop     dword ptr [rax+rax+00h]
0x140010bf1  mov     ebx, eax
0x140010bf3  test    eax, eax
0x140010bf5  jz      short loc_140010C29
0x140010bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140010bfe  cmp     rcx, r13
0x140010c01  jz      short loc_140010C5A
0x140010c03  mov     edx, [rcx+2Ch]
0x140010c06  test    dl, 1
0x140010c09  jz      short loc_140010C29
0x140010c0b  cmp     byte ptr [rcx+29h], 2
0x140010c0f  jb      short loc_140010C29
0x140010c11  mov     rcx, [rcx+18h]
0x140010c15  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010c1c  mov     edx, 3Ch ; '<'
0x140010c21  mov     r9d, eax
0x140010c24  call    WPP_SF_d
0x140010c29  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c30  cmp     rcx, r13
0x140010c33  jz      short loc_140010C5A
0x140010c35  mov     eax, [rcx+2Ch]
0x140010c38  test    al, 1
0x140010c3a  jz      short loc_140010C5A
0x140010c3c  cmp     byte ptr [rcx+29h], 6
0x140010c40  jb      short loc_140010C5A
0x140010c42  mov     rcx, [rcx+18h]
0x140010c46  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010c4d  mov     edx, 3Dh ; '='
0x140010c52  mov     r9d, ebx
0x140010c55  call    WPP_SF_d
0x140010c5a  mov     eax, ebx
0x140010c5c  add     rsp, 30h
0x140010c60  pop     r15
0x140010c62  pop     r14
0x140010c64  pop     r13
0x140010c66  pop     rdi
0x140010c67  pop     rsi
0x140010c68  pop     rbp
0x140010c69  pop     rbx
0x140010c6a  retn
```
