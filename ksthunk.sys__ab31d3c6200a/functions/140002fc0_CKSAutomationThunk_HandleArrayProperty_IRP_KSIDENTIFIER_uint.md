# CKSAutomationThunk::HandleArrayProperty(_IRP *,KSIDENTIFIER *,uint *)

- ea: `0x140002fc0`
- end: `0x14000327a`
- name: `?HandleArrayProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAI@Z`
- size: `698`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140002fc0`
- `0x140004540`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003175`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003175`
- `ntoskrnl!ExFreePool` at `0x14000325a`
- `ntoskrnl!ExFreePool` at `0x14000325a`
- `ks!KsSynchronousIoControlDevice` at `0x1400030e0`
- `ks!KsSynchronousIoControlDevice` at `0x140003133`
- `ks!KsSynchronousIoControlDevice` at `0x1400031dd`
- `ks!KsSynchronousIoControlDevice` at `0x1400030e0`
- `ks!KsSynchronousIoControlDevice` at `0x140003133`
- `ks!KsSynchronousIoControlDevice` at `0x1400031dd`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::HandleArrayProperty(struct _IRP *a1, struct KSIDENTIFIER *a2, unsigned int *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  unsigned int *v4; // r14
  __int64 v8; // rcx
  unsigned int Length; // eax
  ULONG OutSize; // esi
  _QWORD *v11; // rax
  _QWORD *OutBuffer; // rbx
  _QWORD *v13; // rcx
  unsigned int v14; // edx
  unsigned int *j; // rdi
  NTSTATUS v16; // ebx
  ULONG v17; // ebx
  unsigned int *PoolWithTag; // rax
  unsigned int *v19; // rsi
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned __int64 v22; // rdx
  unsigned int *v23; // rsi
  unsigned int i; // ecx
  ULONG BytesReturned; // [rsp+90h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v4 = a3 + 1;
  BytesReturned = 0;
  if ( (a2->Flags & 2) == 0 )
  {
    v16 = KsSynchronousIoControlDevice(
            CurrentStackLocation->FileObject,
            0,
            0x2F0003u,
            a2,
            CurrentStackLocation->Parameters.Create.Options,
            0,
            0,
            &BytesReturned);
    if ( v16 < 0 )
      return (unsigned int)v16;
    if ( !CurrentStackLocation->Parameters.Read.Length )
    {
      a1->IoStatus.Information = (unsigned __int64)BytesReturned >> 1;
      return (unsigned int)v16;
    }
    v17 = BytesReturned;
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1536, BytesReturned, 0x6268534Bu);
    v19 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
    }
    else
    {
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
      memset(PoolWithTag, 0, v17);
    }
    j = v19;
    v16 = KsSynchronousIoControlDevice(
            CurrentStackLocation->FileObject,
            0,
            0x2F0003u,
            a2,
            CurrentStackLocation->Parameters.Create.Options,
            v19,
            BytesReturned,
            &BytesReturned);
    if ( v16 < 0 )
    {
LABEL_33:
      ExFreePool(j);
      return (unsigned int)v16;
    }
    v20 = *v19;
    v21 = *v19 + 1;
    if ( v21 < *v19
      || (v22 = 4LL * v21, v22 > 0xFFFFFFFF)
      || CurrentStackLocation->Parameters.Read.Length < (unsigned int)v22 )
    {
      v16 = -1073741811;
    }
    else
    {
      v23 = v19 + 2;
      *a3 = v20;
      for ( i = 0; i < *a3; ++v4 )
      {
        ++i;
        *v4 = *v23;
        v23 += 2;
        v20 = *a3;
      }
      a1->IoStatus.Information = 4LL * (v20 + 1);
    }
    goto LABEL_32;
  }
  v8 = *a3 + 1;
  if ( (unsigned int)v8 < *a3
    || (unsigned __int64)(4 * v8) > 0xFFFFFFFF
    || 8 * (unsigned __int64)(unsigned int)v8 > 0xFFFFFFFF )
  {
    return (unsigned int)-1073741675;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 4 || Length < 4 * (int)v8 )
    return (unsigned int)-1073741811;
  OutSize = 8 * v8;
  v11 = ExAllocatePoolWithTag((POOL_TYPE)1536, (unsigned int)(8 * v8), 0x6268534Bu);
  OutBuffer = v11;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( v11 )
      goto LABEL_11;
    return (unsigned int)-1073741670;
  }
  if ( !v11 )
    return (unsigned int)-1073741670;
  memset(v11, 0, OutSize);
LABEL_11:
  v13 = OutBuffer + 1;
  v14 = 0;
  *OutBuffer = *a3;
  for ( j = (unsigned int *)OutBuffer; v14 < *a3; ++v13 )
  {
    ++v14;
    *v13 = *v4++;
  }
  v16 = KsSynchronousIoControlDevice(
          CurrentStackLocation->FileObject,
          0,
          0x2F0003u,
          a2,
          CurrentStackLocation->Parameters.Create.Options,
          OutBuffer,
          OutSize,
          &BytesReturned);
LABEL_32:
  if ( j )
    goto LABEL_33;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140002fc0  mov     rax, rsp
0x140002fc3  push    rbx
0x140002fc4  push    rbp
0x140002fc5  push    rsi
0x140002fc6  push    rdi
0x140002fc7  push    r12
0x140002fc9  push    r13
0x140002fcb  push    r14
0x140002fcd  push    r15
0x140002fcf  sub     rsp, 48h
0x140002fd3  mov     rbp, [rcx+0B8h]
0x140002fda  lea     r14, [r8+4]
0x140002fde  xor     edi, edi
0x140002fe0  mov     r12, rdx
0x140002fe3  mov     [rax+8], edi
0x140002fe6  mov     r13, rcx
0x140002fe9  mov     eax, [rdx+14h]
0x140002fec  mov     r15, r8
0x140002fef  test    al, 2
0x140002ff1  jz      loc_140003107
0x140002ff7  mov     eax, [r8]
0x140002ffa  lea     ecx, [rax+1]
0x140002ffd  cmp     ecx, eax
0x140002fff  jb      loc_1400030FD
0x140003005  lea     rdx, ds:0[rcx*4]
0x14000300d  mov     eax, ecx
0x14000300f  mov     ecx, 0FFFFFFFFh
0x140003014  cmp     rdx, rcx
0x140003017  ja      loc_1400030FD
0x14000301d  lea     r8, ds:0[rax*8]
0x140003025  cmp     r8, rcx
0x140003028  ja      loc_1400030FD
0x14000302e  mov     eax, [rbp+8]
0x140003031  cmp     eax, 4
0x140003034  jb      loc_1400030F3
0x14000303a  cmp     eax, edx
0x14000303c  jb      loc_1400030F3
0x140003042  mov     esi, r8d
0x140003045  mov     ecx, 600h; PoolType
0x14000304a  mov     edx, esi; NumberOfBytes
0x14000304c  mov     r8d, 6268534Bh; Tag
0x140003052  call    cs:__imp_ExAllocatePoolWithTag
0x140003059  nop     dword ptr [rax+rax+00h]
0x14000305e  cmp     cs:ExPoolZeroingNativelySupported, dil
0x140003065  mov     rbx, rax
0x140003068  jnz     short loc_140003082
0x14000306a  test    rax, rax
0x14000306d  jz      loc_140003246
0x140003073  mov     r8d, esi; Size
0x140003076  xor     edx, edx; Val
0x140003078  mov     rcx, rax; void *
0x14000307b  call    memset
0x140003080  jmp     short loc_14000308B
0x140003082  test    rbx, rbx
0x140003085  jz      loc_140003246
0x14000308b  mov     eax, [r15]
0x14000308e  lea     rcx, [rbx+8]
0x140003092  xor     edx, edx
0x140003094  mov     [rbx], rax
0x140003097  mov     rdi, rbx
0x14000309a  cmp     [r15], edx
0x14000309d  jbe     short loc_1400030B4
0x14000309f  mov     eax, [r14]
0x1400030a2  inc     edx
0x1400030a4  mov     [rcx], rax
0x1400030a7  lea     r14, [r14+4]
0x1400030ab  lea     rcx, [rcx+8]
0x1400030af  cmp     edx, [r15]
0x1400030b2  jb      short loc_14000309F
0x1400030b4  mov     rcx, [rbp+30h]; FileObject
0x1400030b8  lea     rax, [rsp+88h+arg_0]
0x1400030c0  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x1400030c5  mov     r9, r12; InBuffer
0x1400030c8  mov     eax, [rbp+10h]
0x1400030cb  xor     edx, edx; RequestorMode
0x1400030cd  mov     [rsp+88h+OutSize], esi; OutSize
0x1400030d1  mov     r8d, 2F0003h; IoControl
0x1400030d7  mov     [rsp+88h+OutBuffer], rbx; OutBuffer
0x1400030dc  mov     [rsp+88h+InSize], eax; InSize
0x1400030e0  call    cs:__imp_KsSynchronousIoControlDevice
0x1400030e7  nop     dword ptr [rax+rax+00h]
0x1400030ec  mov     ebx, eax
0x1400030ee  jmp     loc_140003252
0x1400030f3  mov     ebx, 0C000000Dh
0x1400030f8  jmp     loc_140003266
0x1400030fd  mov     ebx, 0C0000095h
0x140003102  jmp     loc_140003266
0x140003107  mov     rcx, [rbp+30h]; FileObject
0x14000310b  lea     rax, [rsp+88h+arg_0]
0x140003113  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x140003118  mov     r9, r12; InBuffer
0x14000311b  mov     eax, [rbp+10h]
0x14000311e  xor     edx, edx; RequestorMode
0x140003120  mov     [rsp+88h+OutSize], edi; OutSize
0x140003124  mov     r8d, 2F0003h; IoControl
0x14000312a  mov     [rsp+88h+OutBuffer], rdi; OutBuffer
0x14000312f  mov     [rsp+88h+InSize], eax; InSize
0x140003133  call    cs:__imp_KsSynchronousIoControlDevice
0x14000313a  nop     dword ptr [rax+rax+00h]
0x14000313f  mov     ebx, eax
0x140003141  test    eax, eax
0x140003143  js      loc_140003266
0x140003149  cmp     [rbp+8], edi
0x14000314c  jnz     short loc_140003161
0x14000314e  mov     eax, [rsp+88h+arg_0]
0x140003155  shr     rax, 1
0x140003158  mov     [r13+38h], rax
0x14000315c  jmp     loc_140003266
0x140003161  mov     ebx, [rsp+88h+arg_0]
0x140003168  mov     r8d, 6268534Bh; Tag
0x14000316e  mov     edx, ebx; NumberOfBytes
0x140003170  mov     ecx, 600h; PoolType
0x140003175  call    cs:__imp_ExAllocatePoolWithTag
0x14000317c  nop     dword ptr [rax+rax+00h]
0x140003181  cmp     cs:ExPoolZeroingNativelySupported, dil
0x140003188  mov     rsi, rax
0x14000318b  jnz     loc_14000323D
0x140003191  test    rax, rax
0x140003194  jz      loc_140003246
0x14000319a  mov     r8d, ebx; Size
0x14000319d  xor     edx, edx; Val
0x14000319f  mov     rcx, rax; void *
0x1400031a2  call    memset
0x1400031a7  mov     rcx, [rbp+30h]; FileObject
0x1400031ab  lea     rax, [rsp+88h+arg_0]
0x1400031b3  mov     [rsp+88h+BytesReturned], rax; BytesReturned
0x1400031b8  mov     r9, r12; InBuffer
0x1400031bb  mov     eax, [rsp+88h+arg_0]
0x1400031c2  xor     edx, edx; RequestorMode
0x1400031c4  mov     [rsp+88h+OutSize], eax; OutSize
0x1400031c8  mov     r8d, 2F0003h; IoControl
0x1400031ce  mov     eax, [rbp+10h]
0x1400031d1  mov     rdi, rsi
0x1400031d4  mov     [rsp+88h+OutBuffer], rsi; OutBuffer
0x1400031d9  mov     [rsp+88h+InSize], eax; InSize
0x1400031dd  call    cs:__imp_KsSynchronousIoControlDevice
0x1400031e4  nop     dword ptr [rax+rax+00h]
0x1400031e9  mov     ebx, eax
0x1400031eb  test    eax, eax
0x1400031ed  js      short loc_140003257
0x1400031ef  mov     eax, [rsi]
0x1400031f1  lea     ecx, [rax+1]
0x1400031f4  cmp     ecx, eax
0x1400031f6  jb      short loc_14000324D
0x1400031f8  mov     edx, ecx
0x1400031fa  mov     ecx, 0FFFFFFFFh
0x1400031ff  shl     rdx, 2
0x140003203  cmp     rdx, rcx
0x140003206  ja      short loc_14000324D
0x140003208  cmp     [rbp+8], edx
0x14000320b  jb      short loc_14000324D
0x14000320d  add     rsi, 8
0x140003211  mov     [r15], eax
0x140003214  xor     ecx, ecx
0x140003216  test    eax, eax
0x140003218  jz      short loc_140003230
0x14000321a  mov     eax, [rsi]
0x14000321c  inc     ecx
0x14000321e  mov     [r14], eax
0x140003221  lea     rsi, [rsi+8]
0x140003225  mov     eax, [r15]
0x140003228  lea     r14, [r14+4]
0x14000322c  cmp     ecx, eax
0x14000322e  jb      short loc_14000321A
0x140003230  lea     ecx, [rax+1]
0x140003233  shl     rcx, 2
0x140003237  mov     [r13+38h], rcx
0x14000323b  jmp     short loc_140003252
0x14000323d  test    rsi, rsi
0x140003240  jnz     loc_1400031A7
0x140003246  mov     ebx, 0C000009Ah
0x14000324b  jmp     short loc_140003266
0x14000324d  mov     ebx, 0C000000Dh
0x140003252  test    rdi, rdi
0x140003255  jz      short loc_140003266
0x140003257  mov     rcx, rdi; P
0x14000325a  call    cs:__imp_ExFreePool
0x140003261  nop     dword ptr [rax+rax+00h]
0x140003266  mov     eax, ebx
0x140003268  add     rsp, 48h
0x14000326c  pop     r15
0x14000326e  pop     r14
0x140003270  pop     r13
0x140003272  pop     r12
0x140003274  pop     rdi
0x140003275  pop     rsi
0x140003276  pop     rbp
0x140003277  pop     rbx
0x140003278  retn
```
