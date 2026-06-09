# PmSplitAndRedirectIo(_DEVICE_EXTENSION *,_IRP *,_LIST_ENTRY *)

- ea: `0x14000e170`
- end: `0x14000e38f`
- name: `?PmSplitAndRedirectIo@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@PEAU_LIST_ENTRY@@@Z`
- size: `543`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _IRP *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x14000e018`
- `0x14000e170`
- `0x140022340`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000e22e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e22e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e1df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e1df`

## pseudocode

```c
__int64 __fastcall PmSplitAndRedirectIo(struct _DEVICE_EXTENSION *a1, struct _IRP *a2, struct _LIST_ENTRY *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  struct _LIST_ENTRY *Flink; // r12
  struct _LIST_ENTRY *Blink; // r15
  int v6; // ebx
  LARGE_INTEGER ByteOffset; // rsi
  ULONG Length; // edi
  char *v10; // rbp
  KSPIN_LOCK *v11; // rax
  KIRQL v12; // dl
  __int64 v13; // r15
  __int64 v14; // rcx
  unsigned int v15; // r15d
  struct _LIST_ENTRY *v17; // [rsp+38h] [rbp-60h]
  KSPIN_LOCK *SpinLock; // [rsp+40h] [rbp-58h]
  struct _DEVICE_EXTENSION *v19; // [rsp+A0h] [rbp+8h]
  char v20; // [rsp+A8h] [rbp+10h]
  struct _LIST_ENTRY *v22; // [rsp+B8h] [rbp+20h]

  v19 = a1;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Flink = a3->Flink;
  Blink = 0;
  v17 = 0;
  v6 = 0;
  v20 = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v10 = (char *)a2->MdlAddress->StartVa + a2->MdlAddress->ByteOffset;
  v22 = 0;
  if ( a3->Flink != a3 )
  {
    v11 = (KSPIN_LOCK *)((char *)a1 + 112);
    SpinLock = (KSPIN_LOCK *)((char *)a1 + 112);
    while ( 1 )
    {
      v12 = KeAcquireSpinLockRaiseToDpc(v11);
      if ( CurrentStackLocation->MajorFunction != 3
        || LODWORD(Flink[3].Flink) == 1 && _bittest64((const signed __int64 *)&Flink[7], 0x3Au) )
      {
        Blink = Flink[3].Blink;
        v22 = Blink;
        v17 = Flink[4].Flink;
      }
      else
      {
        v20 = 1;
      }
      KeReleaseSpinLock(SpinLock, v12);
      if ( v20 )
      {
        v20 = 0;
      }
      else
      {
        if ( (__int64)Blink > ByteOffset.QuadPart )
        {
          v13 = (__int64)Blink - ByteOffset.QuadPart;
          if ( Length <= v13 )
            LODWORD(v13) = Length;
          v6 = PmDiskRedirect(v19, a2, v10, ByteOffset, v13);
          if ( v6 < 0 )
            return (unsigned int)v6;
          v10 += (unsigned int)v13;
          ByteOffset.QuadPart += (unsigned int)v13;
          Length -= v13;
          Blink = v22;
        }
        if ( !Length )
          goto LABEL_25;
        if ( (__int64)Blink <= ByteOffset.QuadPart )
        {
          v14 = ByteOffset.QuadPart - (_QWORD)Blink;
          if ( ByteOffset.QuadPart - (__int64)Blink < (__int64)v17 )
          {
            v15 = (_DWORD)v17 - v14;
            if ( Length <= (__int64)v17 - v14 )
              v15 = Length;
            v6 = PmPartitionRedirect(v19, (struct _PARTITION_EXTENSION *)&Flink[-8].Blink, a2, v10, v14, v15);
            if ( v6 == -1073741822 )
              v6 = PmDiskRedirect(v19, a2, v10, ByteOffset, v15);
            if ( v6 < 0 )
              return (unsigned int)v6;
            ByteOffset.QuadPart += v15;
            v10 += v15;
            Length -= v15;
            if ( !Length )
            {
LABEL_25:
              a1 = v19;
              break;
            }
          }
        }
      }
      Flink = Flink->Flink;
      Blink = v22;
      v11 = SpinLock;
      if ( Flink == a3 )
        goto LABEL_25;
    }
  }
  if ( !Length || (v6 = PmDiskRedirect(a1, a2, v10, ByteOffset, Length), v6 >= 0) )
  {
    if ( LODWORD(a2->IoStatus.Information) != CurrentStackLocation->Parameters.Read.Length )
      return (unsigned int)-1073741595;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e170  mov     [rsp+arg_10], r8
0x14000e175  mov     [rsp+arg_0], rcx
0x14000e17a  push    rbx
0x14000e17b  push    rbp
0x14000e17c  push    rsi
0x14000e17d  push    rdi
0x14000e17e  push    r12
0x14000e180  push    r13
0x14000e182  push    r14
0x14000e184  push    r15
0x14000e186  sub     rsp, 58h
0x14000e18a  mov     r13, [rdx+0B8h]
0x14000e191  xor     eax, eax
0x14000e193  mov     r12, [r8]
0x14000e196  xor     r15d, r15d
0x14000e199  mov     [rsp+98h+var_60], rax
0x14000e19e  xor     ebx, ebx
0x14000e1a0  mov     [rsp+98h+arg_8], al
0x14000e1a7  mov     r14, rdx
0x14000e1aa  mov     rax, [rdx+8]
0x14000e1ae  mov     rsi, [r13+18h]
0x14000e1b2  mov     edi, [r13+8]
0x14000e1b6  mov     [rsp+98h+var_68], r13
0x14000e1bb  mov     ebp, [rax+2Ch]
0x14000e1be  add     rbp, [rax+20h]
0x14000e1c2  mov     [rsp+98h+arg_18], r15
0x14000e1ca  cmp     r12, r8
0x14000e1cd  jz      loc_14000E34F
0x14000e1d3  lea     rax, [rcx+70h]
0x14000e1d7  mov     [rsp+98h+SpinLock], rax
0x14000e1dc  mov     rcx, rax; SpinLock
0x14000e1df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e1e6  nop     dword ptr [rax+rax+00h]
0x14000e1eb  mov     dl, al; NewIrql
0x14000e1ed  mov     rax, [rsp+98h+var_68]
0x14000e1f2  cmp     byte ptr [rax], 3
0x14000e1f5  jnz     short loc_14000E212
0x14000e1f7  cmp     dword ptr [r12+30h], 1
0x14000e1fd  jnz     short loc_14000E208
0x14000e1ff  bt      qword ptr [r12+70h], 3Ah ; ':'
0x14000e206  jb      short loc_14000E212
0x14000e208  mov     [rsp+98h+arg_8], 1
0x14000e210  jmp     short loc_14000E229
0x14000e212  mov     r15, [r12+38h]
0x14000e217  mov     rax, [r12+40h]
0x14000e21c  mov     [rsp+98h+arg_18], r15
0x14000e224  mov     [rsp+98h+var_60], rax
0x14000e229  mov     rcx, [rsp+98h+SpinLock]; SpinLock
0x14000e22e  call    cs:__imp_KeReleaseSpinLock
0x14000e235  nop     dword ptr [rax+rax+00h]
0x14000e23a  cmp     [rsp+98h+arg_8], 0
0x14000e242  jz      short loc_14000E251
0x14000e244  mov     [rsp+98h+arg_8], 0
0x14000e24c  jmp     loc_14000E31F
0x14000e251  cmp     r15, rsi
0x14000e254  jle     short loc_14000E29B
0x14000e256  mov     rcx, [rsp+98h+arg_0]; struct _DEVICE_EXTENSION *
0x14000e25e  sub     r15, rsi
0x14000e261  mov     eax, edi
0x14000e263  mov     r9, rsi; __int64
0x14000e266  cmp     rax, r15
0x14000e269  mov     r8, rbp; void *
0x14000e26c  mov     rdx, r14; struct _IRP *
0x14000e26f  cmovle  r15d, edi
0x14000e273  mov     [rsp+98h+var_78], r15d; unsigned int
0x14000e278  call    ?PmDiskRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@PEAX_JK@Z; PmDiskRedirect(_DEVICE_EXTENSION *,_IRP *,void *,__int64,ulong)
0x14000e27d  mov     ebx, eax
0x14000e27f  test    eax, eax
0x14000e281  js      loc_14000E37B
0x14000e287  mov     ecx, r15d
0x14000e28a  add     rbp, rcx
0x14000e28d  add     rsi, rcx
0x14000e290  sub     edi, r15d
0x14000e293  mov     r15, [rsp+98h+arg_18]
0x14000e29b  test    edi, edi
0x14000e29d  jz      loc_14000E33E
0x14000e2a3  cmp     r15, rsi
0x14000e2a6  jg      short loc_14000E31F
0x14000e2a8  mov     rax, [rsp+98h+var_60]
0x14000e2ad  mov     rcx, rsi
0x14000e2b0  sub     rcx, r15
0x14000e2b3  cmp     rcx, rax
0x14000e2b6  jge     short loc_14000E31F
0x14000e2b8  mov     r13, [rsp+98h+arg_0]
0x14000e2c0  lea     rdx, [r12-78h]; struct _PARTITION_EXTENSION *
0x14000e2c5  mov     r15, rax
0x14000e2c8  mov     r9, rbp; void *
0x14000e2cb  sub     r15, rcx
0x14000e2ce  mov     eax, edi
0x14000e2d0  cmp     rax, r15
0x14000e2d3  mov     r8, r14; struct _IRP *
0x14000e2d6  cmovle  r15d, edi
0x14000e2da  mov     [rsp+98h+var_70], r15d; unsigned int
0x14000e2df  mov     qword ptr [rsp+98h+var_78], rcx; __int64
0x14000e2e4  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x14000e2e7  call    ?PmPartitionRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@PEAU_IRP@@PEAX_JK@Z; PmPartitionRedirect(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *,_IRP *,void *,__int64,ulong)
0x14000e2ec  mov     ebx, eax
0x14000e2ee  cmp     eax, 0C0000002h
0x14000e2f3  jnz     short loc_14000E30D
0x14000e2f5  mov     r9, rsi; __int64
0x14000e2f8  mov     [rsp+98h+var_78], r15d; unsigned int
0x14000e2fd  mov     r8, rbp; void *
0x14000e300  mov     rdx, r14; struct _IRP *
0x14000e303  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x14000e306  call    ?PmDiskRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@PEAX_JK@Z; PmDiskRedirect(_DEVICE_EXTENSION *,_IRP *,void *,__int64,ulong)
0x14000e30b  mov     ebx, eax
0x14000e30d  test    ebx, ebx
0x14000e30f  js      short loc_14000E37B
0x14000e311  mov     eax, r15d
0x14000e314  add     rsi, rax
0x14000e317  add     rbp, rax
0x14000e31a  sub     edi, r15d
0x14000e31d  jz      short loc_14000E342
0x14000e31f  mov     r12, [r12]
0x14000e323  mov     r15, [rsp+98h+arg_18]
0x14000e32b  mov     rax, [rsp+98h+SpinLock]
0x14000e330  cmp     r12, [rsp+98h+arg_10]
0x14000e338  jnz     loc_14000E1DC
0x14000e33e  test    ebx, ebx
0x14000e340  js      short loc_14000E37B
0x14000e342  mov     rcx, [rsp+98h+arg_0]; struct _DEVICE_EXTENSION *
0x14000e34a  mov     r13, [rsp+98h+var_68]
0x14000e34f  test    edi, edi
0x14000e351  jz      short loc_14000E36B
0x14000e353  mov     r9, rsi; __int64
0x14000e356  mov     [rsp+98h+var_78], edi; unsigned int
0x14000e35a  mov     r8, rbp; void *
0x14000e35d  mov     rdx, r14; struct _IRP *
0x14000e360  call    ?PmDiskRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@PEAX_JK@Z; PmDiskRedirect(_DEVICE_EXTENSION *,_IRP *,void *,__int64,ulong)
0x14000e365  mov     ebx, eax
0x14000e367  test    eax, eax
0x14000e369  js      short loc_14000E37B
0x14000e36b  mov     eax, [r13+8]
0x14000e36f  mov     ecx, 0C00000E5h
0x14000e374  cmp     [r14+38h], eax
0x14000e378  cmovnz  ebx, ecx
0x14000e37b  mov     eax, ebx
0x14000e37d  add     rsp, 58h
0x14000e381  pop     r15
0x14000e383  pop     r14
0x14000e385  pop     r13
0x14000e387  pop     r12
0x14000e389  pop     rdi
0x14000e38a  pop     rsi
0x14000e38b  pop     rbp
0x14000e38c  pop     rbx
0x14000e38d  retn
```
