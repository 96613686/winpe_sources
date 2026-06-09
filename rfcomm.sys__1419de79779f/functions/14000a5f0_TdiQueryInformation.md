# TdiQueryInformation

- ea: `0x14000a5f0`
- end: `0x14000a9c9`
- name: `TdiQueryInformation`
- size: `985`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000a5f0`
- `0x14000ab70`
- `0x14000aba8`
- `0x14000b888`
- `0x14001e74c`
- `0x14001ea34`
- `0x14001fc30`
- `0x14001fd40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a752`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a752`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a7f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a81f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a81f`
- `TDI!TdiCopyBufferToMdl` at `0x14000a928`
- `TDI!TdiCopyBufferToMdl` at `0x14000a928`

## string_xrefs

- `0x14000a697`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x14000a7c2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x14000a98d`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiQueryInformation(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v5; // r15
  unsigned int v6; // r12d
  __int64 *v7; // rax
  __int64 v10; // r13
  int v11; // edx
  __int64 v12; // rsi
  int v13; // ebx
  int v14; // r9d
  __int64 v15; // rax
  __int64 v16; // r13
  int v17; // r8d
  unsigned int v19; // [rsp+40h] [rbp-C0h]
  ULONG BytesCopied; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h]
  _QWORD *v22; // [rsp+50h] [rbp-B0h]
  _QWORD SourceBuffer[28]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = 0;
  v6 = 0;
  v22 = a5;
  v7 = *(__int64 **)(a2 + 8);
  v21 = a2;
  BytesCopied = 0;
  v10 = a2;
  v19 = 0;
  if ( v7 )
  {
    do
    {
      v6 += *((_DWORD *)v7 + 10);
      v7 = (__int64 *)*v7;
    }
    while ( v7 );
    v19 = v6;
  }
  memset(SourceBuffer, 0, 0xD8u);
  if ( a3 )
  {
    if ( *(_DWORD *)(a3 + 16) == 1313754947 )
    {
      v12 = a3;
    }
    else
    {
      v12 = 0;
      if ( *(_DWORD *)(a3 + 16) == 1380205633 )
      {
        v5 = a3;
        RefObj_AddRefEx(a3 + 24, 1145981254, 3983, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      }
    }
  }
  else
  {
    v12 = 0;
  }
  switch ( *a4 )
  {
    case 1:
      v13 = -1073741808;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_45;
      v14 = 143;
      goto LABEL_44;
    case 2:
      v13 = 0;
      LODWORD(SourceBuffer[0]) = 512;
      *(_QWORD *)((char *)SourceBuffer + 4) = 65529;
      HIDWORD(SourceBuffer[1]) = 0;
      SourceBuffer[2] = 589835;
      SourceBuffer[3] = 0;
      SourceBuffer[4] = 0;
      goto LABEL_37;
    case 3:
      LODWORD(SourceBuffer[0]) = 1;
      v13 = -1073741503;
      *(_QWORD *)((char *)SourceBuffer + 4) = 0x20001C00000001LL;
      if ( v12 )
      {
        *(_BYTE *)(v12 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v12 + 48));
        v15 = TdiReferenceChannelLocked(v12, 1145981254);
        v16 = v15;
        if ( v15 )
        {
          v13 = 0;
          *(_QWORD *)((char *)&SourceBuffer[1] + 4) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 56) + 72LL) + 120LL);
          HIDWORD(SourceBuffer[4]) = *(_DWORD *)(v12 + 112);
        }
        else
        {
          v5 = TdiReferenceAddrLocked(v12, 1145981254);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v12 + 48), *(_BYTE *)(v12 + 56));
        if ( v16 )
          RefObj_ReleaseEx(v16 + 24, 1145981254, 4081, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
        v10 = v21;
        v6 = v19;
      }
      if ( v5 )
      {
        if ( v13 < 0 )
        {
          *(_BYTE *)(v5 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 48));
          *(_QWORD *)((char *)&SourceBuffer[1] + 4) = *(_QWORD *)(*(_QWORD *)(v5 + 80) + 120LL);
          HIDWORD(SourceBuffer[4]) = *(_DWORD *)(v5 + 112);
          KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 48), *(_BYTE *)(v5 + 56));
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_DDd(WPP_GLOBAL_Control->DeviceExtension, HIDWORD(SourceBuffer[1]), v17, 139);
          v13 = 0;
        }
      }
      else if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          15,
          140,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
      }
      if ( v13 )
        goto LABEL_45;
LABEL_37:
      if ( v6 >= 0x28 )
      {
        TdiCopyBufferToMdl(SourceBuffer, 0, 0x28u, *(PMDL *)(v10 + 8), 0, &BytesCopied);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            144,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
        v13 = -2147483643;
      }
      goto LABEL_45;
  }
  v13 = -1073741808;
  if ( *a4 == 4 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_45;
    v14 = 141;
    goto LABEL_44;
  }
  if ( *a4 == 5 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 142;
LABEL_44:
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      15,
      v14,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  }
LABEL_45:
  *v22 = BytesCopied;
  if ( v5 )
    RefObj_ReleaseEx(v5 + 24, 1145981254, 4161, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000a5f0  mov     [rsp-8+arg_0], rbx
0x14000a5f5  push    rbp
0x14000a5f6  push    rsi
0x14000a5f7  push    rdi
0x14000a5f8  push    r12
0x14000a5fa  push    r13
0x14000a5fc  push    r14
0x14000a5fe  push    r15
0x14000a600  lea     rbp, [rsp-50h]
0x14000a605  sub     rsp, 150h
0x14000a60c  mov     rax, cs:__security_cookie
0x14000a613  xor     rax, rsp
0x14000a616  mov     [rbp+80h+var_40], rax
0x14000a61a  mov     rax, [rbp+80h+arg_20]
0x14000a621  xor     r15d, r15d
0x14000a624  xor     r12d, r12d
0x14000a627  mov     [rsp+180h+var_130], rax
0x14000a62c  mov     rax, [rdx+8]
0x14000a630  mov     rdi, r9
0x14000a633  mov     [rsp+180h+var_138], rdx
0x14000a638  mov     rbx, r8
0x14000a63b  mov     [rsp+180h+var_13C], r15d
0x14000a640  mov     r13, rdx
0x14000a643  mov     [rsp+180h+var_140], r12d
0x14000a648  test    rax, rax
0x14000a64b  jz      short loc_14000A65E
0x14000a64d  add     r12d, [rax+28h]
0x14000a651  mov     rax, [rax]
0x14000a654  test    rax, rax
0x14000a657  jnz     short loc_14000A64D
0x14000a659  mov     [rsp+180h+var_140], r12d
0x14000a65e  xor     edx, edx; Val
0x14000a660  lea     rcx, [rsp+180h+SourceBuffer]; void *
0x14000a665  mov     r8d, 0D8h; Size
0x14000a66b  call    memset
0x14000a670  test    rbx, rbx
0x14000a673  jz      short loc_14000A6AE
0x14000a675  cmp     dword ptr [rbx+10h], 4E4E4F43h
0x14000a67c  jnz     short loc_14000A683
0x14000a67e  mov     rsi, rbx
0x14000a681  jmp     short loc_14000A6B0
0x14000a683  xor     esi, esi
0x14000a685  cmp     dword ptr [rbx+10h], 52444441h
0x14000a68c  jnz     short loc_14000A6B0
0x14000a68e  lea     rcx, [rbx+18h]
0x14000a692  mov     edx, 444E4946h
0x14000a697  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000a69e  mov     r8d, 0F8Fh
0x14000a6a4  mov     r15, rbx
0x14000a6a7  call    RefObj_AddRefEx
0x14000a6ac  jmp     short loc_14000A6B0
0x14000a6ae  xor     esi, esi
0x14000a6b0  mov     ecx, [rdi]
0x14000a6b2  sub     ecx, 1
0x14000a6b5  jz      loc_14000A936
0x14000a6bb  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a6c2  lea     r14, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000a6c9  sub     ecx, 1
0x14000a6cc  jz      loc_14000A8A8
0x14000a6d2  sub     ecx, 1
0x14000a6d5  jz      short loc_14000A728
0x14000a6d7  mov     ebx, 0C0000010h
0x14000a6dc  sub     ecx, 1
0x14000a6df  jz      short loc_14000A709
0x14000a6e1  cmp     ecx, 1
0x14000a6e4  jnz     loc_14000A973
0x14000a6ea  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a6f1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a6f8  jz      loc_14000A973
0x14000a6fe  mov     r9d, 8Eh
0x14000a704  jmp     loc_14000A951
0x14000a709  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a710  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a717  jz      loc_14000A973
0x14000a71d  mov     r9d, 8Dh
0x14000a723  jmp     loc_14000A951
0x14000a728  mov     [rsp+180h+SourceBuffer], 1
0x14000a730  mov     ebx, 0C0000141h
0x14000a735  mov     dword ptr [rsp+180h+var_11C], 1
0x14000a73d  mov     dword ptr [rsp+180h+var_11C+4], 20001Ch
0x14000a745  test    rsi, rsi
0x14000a748  jz      loc_14000A7DE
0x14000a74e  lea     rcx, [rsi+30h]; SpinLock
0x14000a752  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a759  nop     dword ptr [rax+rax+00h]
0x14000a75e  mov     edx, 444E4946h
0x14000a763  mov     rcx, rsi
0x14000a766  mov     [rsi+38h], al
0x14000a769  call    TdiReferenceChannelLocked
0x14000a76e  mov     r13, rax
0x14000a771  test    rax, rax
0x14000a774  jz      short loc_14000A791
0x14000a776  mov     rcx, [rax+38h]
0x14000a77a  xor     ebx, ebx
0x14000a77c  mov     rdx, [rcx+48h]
0x14000a780  mov     rcx, [rdx+78h]
0x14000a784  mov     [rsp+180h+var_114], rcx
0x14000a789  mov     ecx, [rsi+70h]
0x14000a78c  mov     [rbp+80h+var_FC], ecx
0x14000a78f  jmp     short loc_14000A7A1
0x14000a791  mov     edx, 444E4946h
0x14000a796  mov     rcx, rsi
0x14000a799  call    TdiReferenceAddrLocked
0x14000a79e  mov     r15, rax
0x14000a7a1  mov     dl, [rsi+38h]; NewIrql
0x14000a7a4  lea     rcx, [rsi+30h]; SpinLock
0x14000a7a8  call    cs:__imp_KeReleaseSpinLock
0x14000a7af  nop     dword ptr [rax+rax+00h]
0x14000a7b4  test    r13, r13
0x14000a7b7  jz      short loc_14000A7D4
0x14000a7b9  lea     rcx, [r13+18h]
0x14000a7bd  mov     edx, 444E4946h
0x14000a7c2  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000a7c9  mov     r8d, 0FF1h
0x14000a7cf  call    RefObj_ReleaseEx
0x14000a7d4  mov     r13, [rsp+180h+var_138]
0x14000a7d9  mov     r12d, [rsp+180h+var_140]
0x14000a7de  test    r15, r15
0x14000a7e1  jz      loc_14000A86C
0x14000a7e7  test    ebx, ebx
0x14000a7e9  jns     loc_14000A898
0x14000a7ef  lea     rcx, [r15+30h]; SpinLock
0x14000a7f3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a7fa  nop     dword ptr [rax+rax+00h]
0x14000a7ff  mov     [r15+38h], al
0x14000a803  lea     rcx, [r15+30h]; SpinLock
0x14000a807  mov     rax, [r15+50h]
0x14000a80b  mov     rdx, [rax+78h]
0x14000a80f  mov     [rsp+180h+var_114], rdx
0x14000a814  mov     eax, [r15+70h]
0x14000a818  mov     [rbp+80h+var_FC], eax
0x14000a81b  mov     dl, [r15+38h]; NewIrql
0x14000a81f  call    cs:__imp_KeReleaseSpinLock
0x14000a826  nop     dword ptr [rax+rax+00h]
0x14000a82b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a832  jz      short loc_14000A868
0x14000a834  mov     rdx, [rsp+180h+var_114]
0x14000a839  mov     r9d, 8Bh
0x14000a83f  mov     rax, rdx
0x14000a842  shr     rax, 20h
0x14000a846  movzx   ecx, ax
0x14000a849  mov     eax, [rbp+80h+var_FC]
0x14000a84c  mov     [rsp+180h+var_148], eax
0x14000a850  mov     [rsp+180h+var_150], edx
0x14000a854  mov     dword ptr [rsp+180h+BytesCopied], ecx
0x14000a858  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a85f  mov     rcx, [rcx+40h]
0x14000a863  call    WPP_RECORDER_SF_DDd
0x14000a868  xor     ebx, ebx
0x14000a86a  jmp     short loc_14000A898
0x14000a86c  test    ebx, ebx
0x14000a86e  jns     short loc_14000A898
0x14000a870  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a877  jz      short loc_14000A898
0x14000a879  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a880  mov     r9d, 8Ch
0x14000a886  mov     qword ptr [rsp+180h+DestinationOffset], r14
0x14000a88b  mov     rcx, [rcx+40h]
0x14000a88f  lea     r8d, [r9-7Dh]
0x14000a893  call    WPP_RECORDER_SF_
0x14000a898  mov     r8d, 28h ; '('
0x14000a89e  test    ebx, ebx
0x14000a8a0  jnz     loc_14000A973
0x14000a8a6  jmp     short loc_14000A8D5
0x14000a8a8  xor     ebx, ebx
0x14000a8aa  mov     [rsp+180h+SourceBuffer], 200h
0x14000a8b2  mov     [rsp+180h+var_11C], 0FFF9h
0x14000a8bb  mov     dword ptr [rsp+180h+var_114], ebx
0x14000a8bf  mov     [rsp+180h+var_114+4], 9000Bh
0x14000a8c8  lea     r8d, [rbx+28h]; SourceBytesToCopy
0x14000a8cc  mov     [rsp+180h+var_108], rbx
0x14000a8d1  mov     [rbp-80h], rbx
0x14000a8d5  cmp     r12d, r8d
0x14000a8d8  jnb     short loc_14000A90B
0x14000a8da  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a8e1  jz      short loc_14000A904
0x14000a8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8ea  mov     r9d, 90h
0x14000a8f0  mov     r8d, 1
0x14000a8f6  mov     qword ptr [rsp+180h+DestinationOffset], r14
0x14000a8fb  mov     rcx, [rcx+40h]
0x14000a8ff  call    WPP_RECORDER_SF_
0x14000a904  mov     ebx, 80000005h
0x14000a909  jmp     short loc_14000A973
0x14000a90b  mov     r9, [r13+8]; DestinationMdlChain
0x14000a90f  lea     rax, [rsp+180h+var_13C]
0x14000a914  mov     [rsp+180h+BytesCopied], rax; BytesCopied
0x14000a919  lea     rcx, [rsp+180h+SourceBuffer]; SourceBuffer
0x14000a91e  xor     edx, edx; SourceOffset
0x14000a920  mov     [rsp+180h+DestinationOffset], 0; DestinationOffset
0x14000a928  call    cs:__imp_TdiCopyBufferToMdl
0x14000a92f  nop     dword ptr [rax+rax+00h]
0x14000a934  jmp     short loc_14000A973
0x14000a936  mov     ebx, 0C0000010h
0x14000a93b  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a942  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a949  jz      short loc_14000A973
0x14000a94b  mov     r9d, 8Fh
0x14000a951  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a958  lea     r14, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000a95f  mov     r8d, 0Fh
0x14000a965  mov     qword ptr [rsp+180h+DestinationOffset], r14
0x14000a96a  mov     rcx, [rcx+40h]
0x14000a96e  call    WPP_RECORDER_SF_
0x14000a973  mov     rax, [rsp+180h+var_130]
0x14000a978  mov     ecx, [rsp+180h+var_13C]
0x14000a97c  mov     [rax], rcx
0x14000a97f  test    r15, r15
0x14000a982  jz      short loc_14000A99F
0x14000a984  lea     rcx, [r15+18h]
0x14000a988  mov     edx, 444E4946h
0x14000a98d  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000a994  mov     r8d, 1041h
0x14000a99a  call    RefObj_ReleaseEx
0x14000a99f  mov     eax, ebx
0x14000a9a1  mov     rcx, [rbp+80h+var_40]
0x14000a9a5  xor     rcx, rsp; StackCookie
0x14000a9a8  call    __security_check_cookie
0x14000a9ad  mov     rbx, [rsp+180h+arg_0]
0x14000a9b5  add     rsp, 150h
0x14000a9bc  pop     r15
0x14000a9be  pop     r14
0x14000a9c0  pop     r13
0x14000a9c2  pop     r12
0x14000a9c4  pop     rdi
0x14000a9c5  pop     rsi
0x14000a9c6  pop     rbp
0x14000a9c7  retn
```
