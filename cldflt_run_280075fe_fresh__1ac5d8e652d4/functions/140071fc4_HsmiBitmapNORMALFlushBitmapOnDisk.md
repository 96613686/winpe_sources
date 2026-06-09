# HsmiBitmapNORMALFlushBitmapOnDisk

- ea: `0x140071fc4`
- end: `0x140072436`
- name: `HsmiBitmapNORMALFlushBitmapOnDisk`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14000a940`

## callees

- `0x140003c50`
- `0x140005e84`
- `0x140006170`
- `0x140009c7c`
- `0x140018e90`
- `0x14001a324`
- `0x14001b85c`
- `0x14001e280`
- `0x14001e580`
- `0x140036400`
- `0x140071fc4`
- `0x140072eec`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400720d7`
- `ntoskrnl!RtlComputeCrc32` at `0x1400720d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072290`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072290`
- `ntoskrnl!ExAllocatePool2` at `0x14007200e`
- `ntoskrnl!ExAllocatePool2` at `0x14007200e`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALFlushBitmapOnDisk(_QWORD *a1, int a2, __int64 *a3)
{
  __int64 v3; // r12
  _QWORD *v4; // rdi
  UCHAR *Pool2; // rax
  UCHAR *v6; // r14
  _QWORD *v7; // r15
  PVOID v8; // rcx
  PUCHAR v9; // rbx
  __int64 v10; // r9
  int v11; // ebx
  int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r14d
  __int64 v17; // r15
  _QWORD *v18; // rdi
  __int64 v20; // rcx
  PDEVICE_OBJECT v21; // rcx
  int v22; // edx
  int v23; // [rsp+20h] [rbp-C8h]
  __int64 v24; // [rsp+38h] [rbp-B0h]
  PUCHAR Buffer; // [rsp+40h] [rbp-A8h] BYREF
  int v26; // [rsp+48h] [rbp-A0h]
  PVOID v27[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v28; // [rsp+60h] [rbp-88h]
  PVOID P; // [rsp+68h] [rbp-80h]
  _QWORD *v30; // [rsp+70h] [rbp-78h]
  __int64 v31; // [rsp+78h] [rbp-70h]
  _QWORD *v32; // [rsp+80h] [rbp-68h]
  _QWORD *v33; // [rsp+90h] [rbp-58h]
  _OWORD v34[4]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v36; // [rsp+F8h] [rbp+10h] BYREF
  __int64 *v37; // [rsp+100h] [rbp+18h]
  int v38; // [rsp+108h] [rbp+20h]

  v37 = a3;
  LODWORD(v3) = a2;
  v4 = a1;
  Buffer = 0;
  v27[0] = 0;
  v27[1] = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(258, 4096, 1833071432);
  v6 = Pool2;
  P = Pool2;
  if ( Pool2 )
  {
    v7 = v4;
    v30 = v4;
    v8 = Pool2;
    v33 = v4 + 18;
    v28 = v4[18] + 1LL;
    while ( 1 )
    {
      LOBYTE(v36) = 0;
      v3 = (unsigned int)(v3 - 1);
      v38 = v3;
      Buffer = v6;
      memset(v8, 0, 0x1000u);
      *(_DWORD *)Buffer = 1884124226;
      Buffer[4] = 1;
      Buffer[5] = 3;
      *((_WORD *)Buffer + 3) = _byteswap_ushort(*((_WORD *)Buffer + 2));
      *((_DWORD *)Buffer + 2) = v3;
      *((_QWORD *)Buffer + 2) = v28;
      v9 = Buffer;
      *((_DWORD *)v9 + 1023) = RtlComputeCrc32(0, Buffer, 0xFFCu);
      v31 = 8 * v3;
      v32 = v4 + 20;
      LOBYTE(v10) = 1;
      v11 = HsmpFileCachePreparePinWrite(
              *(PFILE_OBJECT *)(v4[20] + 8 * v3 + 8),
              (union _LARGE_INTEGER)(((*((_QWORD *)Buffer + 2) + 1LL) % 2) << 12),
              8 * v3,
              v10,
              v23,
              &v27[1],
              (PVOID *)&Buffer,
              (BOOLEAN *)&v36);
      v26 = v11;
      HsmDbgBreakOnStatus((unsigned int)v11);
      if ( v11 < 0 )
        break;
      LODWORD(v27[0]) = 1;
      memmove(Buffer, v6, 0x1000u);
      v11 = HsmpFileCacheSetAddressRangeModified(Buffer);
      HsmDbgBreakOnStatus((unsigned int)v11);
      if ( v11 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_22;
        }
        v22 = 87;
LABEL_26:
        LODWORD(v24) = v11;
        goto LABEL_27;
      }
      v34[0] = *(_OWORD *)v27;
      HsmIBitmapNORMALUnpinBlock(v34);
      LODWORD(v27[0]) = 0;
      Buffer = 0;
      v16 = 0;
      v17 = v31;
      v18 = v32;
      do
      {
        v11 = HsmpFileCacheFlush(*(_QWORD *)(v17 + *v18 + 8), v13, v14, v15);
        LODWORD(v36) = v11;
        HsmDbgBreakOnStatus((unsigned int)v11);
        if ( v11 != -1073741740 )
          break;
        ++v16;
        v11 = -1073741740;
      }
      while ( v16 < 5 );
      v4 = a1;
      v6 = (UCHAR *)P;
      v7 = v30;
      if ( v11 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v22 = 88;
          v12 = v36;
          LODWORD(v24) = v36;
LABEL_27:
          WPP_SF_qisdd(v21->AttachedDevice, v22, v12, (_DWORD)v4, *v7, (__int64)(v4 + 4), v3, v24, Buffer);
        }
LABEL_22:
        v11 = HsmiBitmapTranslateIOStatus(v21, (unsigned int)v11);
        v20 = (unsigned int)v11;
        goto LABEL_20;
      }
      v8 = P;
      if ( !(_DWORD)v3 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_qisi(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)a1 + 32,
            v14,
            (_DWORD)a1,
            *v30,
            (__int64)(a1 + 4),
            *v33);
        }
        *v37 = v28;
        goto LABEL_14;
      }
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_22;
    }
    v22 = 85;
    goto LABEL_26;
  }
  v11 = -1073741670;
  v20 = 3221225626LL;
LABEL_20:
  HsmDbgBreakOnStatus(v20);
LABEL_14:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6D427348u);
  if ( LODWORD(v27[0]) )
  {
    v34[0] = *(_OWORD *)v27;
    HsmIBitmapNORMALUnpinBlock(v34);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140071fc4  mov     [rsp+arg_10], r8
0x140071fc9  mov     [rsp+arg_0], rcx
0x140071fce  push    rbx
0x140071fcf  push    rdi
0x140071fd0  push    r12
0x140071fd2  push    r13
0x140071fd4  push    r14
0x140071fd6  push    r15
0x140071fd8  sub     rsp, 0B8h
0x140071fdf  mov     r12d, edx
0x140071fe2  mov     rdi, rcx
0x140071fe5  mov     [rsp+0E8h+Buffer], 0
0x140071fee  mov     [rsp+0E8h+var_98], 0
0x140071ff7  xor     eax, eax
0x140071ff9  mov     [rsp+0E8h+var_98+8], rax
0x140071ffe  mov     edx, 1000h
0x140072003  mov     ecx, 102h
0x140072008  mov     r8d, 6D427348h
0x14007200e  call    cs:__imp_ExAllocatePool2
0x140072015  nop     dword ptr [rax+rax+00h]
0x14007201a  mov     r14, rax
0x14007201d  mov     [rsp+0E8h+P], rax
0x140072022  test    rax, rax
0x140072025  jz      loc_1400722BC
0x14007202b  mov     r15, rdi
0x14007202e  mov     [rsp+0E8h+var_78], rdi
0x140072033  mov     rcx, rax; void *
0x140072036  lea     rax, [rdi+90h]
0x14007203d  mov     [rsp+0E8h+var_58], rax
0x140072045  mov     rax, [rax]
0x140072048  inc     rax
0x14007204b  mov     [rsp+0E8h+var_88], rax
0x140072050  mov     r13d, 2
0x140072056  mov     byte ptr [rsp+0E8h+arg_8], 0
0x14007205e  dec     r12d
0x140072061  mov     [rsp+0E8h+arg_18], r12d
0x140072069  mov     [rsp+0E8h+Buffer], r14
0x14007206e  xor     edx, edx; Val
0x140072070  mov     r8d, 1000h; Size
0x140072076  call    memset
0x14007207b  mov     rax, [rsp+0E8h+Buffer]
0x140072080  mov     dword ptr [rax], 704D7442h
0x140072086  mov     rax, [rsp+0E8h+Buffer]
0x14007208b  mov     byte ptr [rax+4], 1
0x14007208f  mov     rax, [rsp+0E8h+Buffer]
0x140072094  mov     byte ptr [rax+5], 3
0x140072098  mov     rdx, [rsp+0E8h+Buffer]
0x14007209d  movzx   ecx, byte ptr [rdx+4]
0x1400720a1  shl     cx, 8
0x1400720a5  movzx   eax, byte ptr [rdx+5]
0x1400720a9  or      cx, ax
0x1400720ac  mov     [rdx+6], cx
0x1400720b0  mov     rax, [rsp+0E8h+Buffer]
0x1400720b5  mov     [rax+8], r12d
0x1400720b9  mov     rax, [rsp+0E8h+Buffer]
0x1400720be  mov     rcx, [rsp+0E8h+var_88]
0x1400720c3  mov     [rax+10h], rcx
0x1400720c7  mov     rbx, [rsp+0E8h+Buffer]
0x1400720cc  mov     r8d, 0FFCh; Length
0x1400720d2  mov     rdx, rbx; Buffer
0x1400720d5  xor     ecx, ecx; InitialCrc
0x1400720d7  call    cs:__imp_RtlComputeCrc32
0x1400720de  nop     dword ptr [rax+rax+00h]
0x1400720e3  mov     [rbx+0FFCh], eax
0x1400720e9  lea     r8, ds:0[r12*8]
0x1400720f1  mov     [rsp+0E8h+var_70], r8
0x1400720f6  lea     rcx, [rdi+0A0h]
0x1400720fd  mov     [rsp+0E8h+var_68], rcx
0x140072105  mov     rax, [rsp+0E8h+Buffer]
0x14007210a  mov     rax, [rax+10h]
0x14007210e  inc     rax
0x140072111  cqo
0x140072113  idiv    r13
0x140072116  shl     rdx, 0Ch
0x14007211a  mov     rcx, [rcx]
0x14007211d  lea     rax, [rsp+0E8h+arg_8]
0x140072125  mov     [rsp+0E8h+var_B0], rax; __int64
0x14007212a  lea     rax, [rsp+0E8h+Buffer]
0x14007212f  mov     [rsp+0E8h+var_B8], rax; PVOID *
0x140072134  lea     rax, [rsp+0E8h+var_98+8]
0x140072139  mov     [rsp+0E8h+var_C0], rax; PVOID *
0x14007213e  mov     r9b, 1
0x140072141  mov     rcx, [rcx+r8+8]; FileObject
0x140072146  call    HsmpFileCachePreparePinWrite
0x14007214b  mov     ebx, eax
0x14007214d  mov     [rsp+0E8h+var_A0], eax
0x140072151  mov     ecx, eax
0x140072153  call    HsmDbgBreakOnStatus
0x140072158  test    ebx, ebx
0x14007215a  js      loc_1400722CA
0x140072160  mov     dword ptr [rsp+0E8h+var_98], 1
0x140072168  mov     r8d, 1000h; Size
0x14007216e  mov     rdx, r14; Src
0x140072171  mov     rcx, [rsp+0E8h+Buffer]; void *
0x140072176  call    memmove
0x14007217b  jmp     short loc_1400721A1
0x14007217d  mov     r13d, 2
0x140072183  mov     rdi, [rsp+0E8h+arg_0]
0x14007218b  mov     ebx, [rsp+0E8h+var_A0]
0x14007218f  mov     r12d, [rsp+0E8h+arg_18]
0x140072197  mov     r14, [rsp+0E8h+P]
0x14007219c  mov     r15, [rsp+0E8h+var_78]
0x1400721a1  test    ebx, ebx
0x1400721a3  js      loc_14007233F
0x1400721a9  mov     rcx, [rsp+0E8h+Buffer]; Address
0x1400721ae  call    HsmpFileCacheSetAddressRangeModified
0x1400721b3  mov     ebx, eax
0x1400721b5  mov     ecx, eax
0x1400721b7  call    HsmDbgBreakOnStatus
0x1400721bc  test    ebx, ebx
0x1400721be  js      loc_14007236A
0x1400721c4  movaps  xmm0, xmmword ptr [rsp+0E8h+var_98]
0x1400721c9  movdqa  [rsp+0E8h+var_48], xmm0
0x1400721d2  lea     rcx, [rsp+0E8h+var_48]
0x1400721da  call    HsmIBitmapNORMALUnpinBlock
0x1400721df  mov     dword ptr [rsp+0E8h+var_98], 0
0x1400721e7  mov     [rsp+0E8h+Buffer], 0
0x1400721f0  xor     r14d, r14d
0x1400721f3  mov     r15, [rsp+0E8h+var_70]
0x1400721f8  mov     rdi, [rsp+0E8h+var_68]
0x140072200  mov     rcx, [rdi]
0x140072203  mov     rcx, [r15+rcx+8]
0x140072208  call    HsmpFileCacheFlush
0x14007220d  mov     ebx, eax
0x14007220f  mov     dword ptr [rsp+0E8h+arg_8], eax
0x140072216  mov     ecx, eax
0x140072218  call    HsmDbgBreakOnStatus
0x14007221d  cmp     ebx, 0C0000054h
0x140072223  jz      loc_14007239C
0x140072229  test    ebx, ebx
0x14007222b  mov     rdi, [rsp+0E8h+arg_0]
0x140072233  mov     r14, [rsp+0E8h+P]
0x140072238  mov     r15, [rsp+0E8h+var_78]
0x14007223d  js      loc_1400723B3
0x140072243  test    r12d, r12d
0x140072246  mov     rcx, r14
0x140072249  jnz     loc_140072056
0x14007224f  lea     rax, WPP_GLOBAL_Control
0x140072256  mov     rcx, cs:WPP_GLOBAL_Control
0x14007225d  cmp     rcx, rax
0x140072260  jz      short loc_140072273
0x140072262  mov     eax, [rcx+2Ch]
0x140072265  test    al, 1
0x140072267  jz      short loc_140072273
0x140072269  cmp     byte ptr [rcx+29h], 5
0x14007226d  jnb     loc_1400723E4
0x140072273  mov     rax, [rsp+0E8h+var_88]
0x140072278  mov     rcx, [rsp+0E8h+arg_10]
0x140072280  mov     [rcx], rax
0x140072283  test    r14, r14
0x140072286  jz      short loc_14007229C
0x140072288  mov     edx, 6D427348h; Tag
0x14007228d  mov     rcx, r14; P
0x140072290  call    cs:__imp_ExFreePoolWithTag
0x140072297  nop     dword ptr [rax+rax+00h]
0x14007229c  cmp     dword ptr [rsp+0E8h+var_98], 0
0x1400722a1  jnz     loc_140072416
0x1400722a7  mov     eax, ebx
0x1400722a9  add     rsp, 0B8h
0x1400722b0  pop     r15
0x1400722b2  pop     r14
0x1400722b4  pop     r13
0x1400722b6  pop     r12
0x1400722b8  pop     rdi
0x1400722b9  pop     rbx
0x1400722ba  retn
0x1400722bc  mov     ebx, 0C000009Ah
0x1400722c1  mov     ecx, ebx
0x1400722c3  call    HsmDbgBreakOnStatus
0x1400722c8  jmp     short loc_140072283
0x1400722ca  lea     rax, WPP_GLOBAL_Control
0x1400722d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400722d8  cmp     rcx, rax
0x1400722db  jnz     short loc_1400722EA
0x1400722dd  mov     edx, ebx
0x1400722df  call    HsmiBitmapTranslateIOStatus
0x1400722e4  mov     ebx, eax
0x1400722e6  mov     ecx, eax
0x1400722e8  jmp     short loc_1400722C3
0x1400722ea  mov     eax, [rcx+2Ch]
0x1400722ed  test    al, 1
0x1400722ef  jz      short loc_1400722DD
0x1400722f1  cmp     [rcx+29h], r13b
0x1400722f5  jb      short loc_1400722DD
0x1400722f7  mov     edx, 55h ; 'U'
0x1400722fc  jmp     short loc_140072303
0x1400722fe  mov     edx, 57h ; 'W'
0x140072303  mov     dword ptr [rsp+0E8h+var_B0], ebx
0x140072307  jmp     short loc_14007231B
0x140072309  mov     edx, 58h ; 'X'
0x14007230e  mov     r8d, dword ptr [rsp+0E8h+arg_8]
0x140072316  mov     dword ptr [rsp+0E8h+var_B0], r8d
0x14007231b  lea     rax, [rdi+20h]
0x14007231f  mov     dword ptr [rsp+0E8h+var_B8], r12d
0x140072324  mov     [rsp+0E8h+var_C0], rax
0x140072329  mov     rax, [r15]
0x14007232c  mov     [rsp+0E8h+var_C8], rax
0x140072331  mov     r9, rdi
0x140072334  mov     rcx, [rcx+18h]
0x140072338  call    WPP_SF_qisdd
0x14007233d  jmp     short loc_1400722DD
0x14007233f  lea     rax, WPP_GLOBAL_Control
0x140072346  mov     rcx, cs:WPP_GLOBAL_Control
0x14007234d  cmp     rcx, rax
0x140072350  jz      short loc_1400722DD
0x140072352  mov     eax, [rcx+2Ch]
0x140072355  test    al, 1
0x140072357  jz      short loc_1400722DD
0x140072359  cmp     [rcx+29h], r13b
0x14007235d  jb      loc_1400722DD
0x140072363  mov     edx, 56h ; 'V'
0x140072368  jmp     short loc_140072303
0x14007236a  lea     rax, WPP_GLOBAL_Control
0x140072371  mov     rcx, cs:WPP_GLOBAL_Control
0x140072378  cmp     rcx, rax
0x14007237b  jz      loc_1400722DD
0x140072381  mov     edx, [rcx+2Ch]
0x140072384  test    dl, 1
0x140072387  jz      loc_1400722DD
0x14007238d  cmp     [rcx+29h], r13b
0x140072391  jb      loc_1400722DD
0x140072397  jmp     loc_1400722FE
0x14007239c  inc     r14d
0x14007239f  mov     ebx, 0C0000054h
0x1400723a4  cmp     r14d, 5
0x1400723a8  jl      loc_140072200
0x1400723ae  jmp     loc_140072229
0x1400723b3  lea     rax, WPP_GLOBAL_Control
0x1400723ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723c1  cmp     rcx, rax
0x1400723c4  jz      loc_1400722DD
0x1400723ca  mov     eax, [rcx+2Ch]
0x1400723cd  test    al, 1
0x1400723cf  jz      loc_1400722DD
0x1400723d5  cmp     [rcx+29h], r13b
0x1400723d9  jb      loc_1400722DD
0x1400723df  jmp     loc_140072309
0x1400723e4  lea     rdx, [rdi+20h]
0x1400723e8  mov     rax, [rsp+0E8h+var_58]
0x1400723f0  mov     rax, [rax]
0x1400723f3  mov     [rsp+0E8h+var_B8], rax
0x1400723f8  mov     [rsp+0E8h+var_C0], rdx
0x1400723fd  mov     rax, [r15]
0x140072400  mov     [rsp+0E8h+var_C8], rax
0x140072405  mov     r9, rdi
0x140072408  mov     rcx, [rcx+18h]
0x14007240c  call    WPP_SF_qisi
0x140072411  jmp     loc_140072273
0x140072416  movaps  xmm0, xmmword ptr [rsp+0E8h+var_98]
0x14007241b  movdqa  [rsp+0E8h+var_48], xmm0
0x140072424  lea     rcx, [rsp+0E8h+var_48]
0x14007242c  call    HsmIBitmapNORMALUnpinBlock
0x140072431  jmp     loc_1400722A7
0x1400867af  push    rbp
0x1400867b1  sub     rsp, 40h
0x1400867b5  mov     rbp, rdx
0x1400867b8  lea     rdx, [rbp+48h]
0x1400867bc  call    HsmFileCacheExceptionFilter
0x1400867c1  nop
0x1400867c2  add     rsp, 40h
0x1400867c6  pop     rbp
0x1400867c7  retn
```
