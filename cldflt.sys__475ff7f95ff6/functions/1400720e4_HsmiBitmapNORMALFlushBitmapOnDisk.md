# HsmiBitmapNORMALFlushBitmapOnDisk

- ea: `0x1400720e4`
- end: `0x140072556`
- name: `HsmiBitmapNORMALFlushBitmapOnDisk`
- size: `1138`
- prototype: `__int64 __fastcall(_QWORD *, int, __int64 *)`
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
- `0x140018f10`
- `0x14001a3a4`
- `0x14001b8dc`
- `0x14001e300`
- `0x14001e600`
- `0x140036400`
- `0x1400720e4`
- `0x14007300c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400721f7`
- `ntoskrnl!RtlComputeCrc32` at `0x1400721f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400723b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400723b0`
- `ntoskrnl!ExAllocatePool2` at `0x14007212e`
- `ntoskrnl!ExAllocatePool2` at `0x14007212e`

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
  int v10; // ebx
  int v11; // r8d
  int v12; // r14d
  __int64 v13; // r15
  _QWORD *v14; // rdi
  int v15; // r8d
  int v17; // ecx
  PDEVICE_OBJECT v18; // rcx
  int v19; // edx
  int v20; // [rsp+20h] [rbp-C8h]
  PUCHAR Buffer; // [rsp+40h] [rbp-A8h] BYREF
  int v22; // [rsp+48h] [rbp-A0h]
  PVOID v23[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v24; // [rsp+60h] [rbp-88h]
  PVOID P; // [rsp+68h] [rbp-80h]
  _QWORD *v26; // [rsp+70h] [rbp-78h]
  __int64 v27; // [rsp+78h] [rbp-70h]
  _QWORD *v28; // [rsp+80h] [rbp-68h]
  _QWORD *v29; // [rsp+90h] [rbp-58h]
  _OWORD v30[4]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v32; // [rsp+F8h] [rbp+10h] BYREF
  __int64 *v33; // [rsp+100h] [rbp+18h]
  int v34; // [rsp+108h] [rbp+20h]

  v33 = a3;
  LODWORD(v3) = a2;
  v4 = a1;
  Buffer = 0;
  v23[0] = 0;
  v23[1] = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(258, 4096, 1833071432);
  v6 = Pool2;
  P = Pool2;
  if ( Pool2 )
  {
    v7 = v4;
    v26 = v4;
    v8 = Pool2;
    v29 = v4 + 18;
    v24 = v4[18] + 1LL;
    while ( 1 )
    {
      LOBYTE(v32) = 0;
      v3 = (unsigned int)(v3 - 1);
      v34 = v3;
      Buffer = v6;
      memset(v8, 0, 0x1000u);
      *(_DWORD *)Buffer = 1884124226;
      Buffer[4] = 1;
      Buffer[5] = 3;
      *((_WORD *)Buffer + 3) = _byteswap_ushort(*((_WORD *)Buffer + 2));
      *((_DWORD *)Buffer + 2) = v3;
      *((_QWORD *)Buffer + 2) = v24;
      v9 = Buffer;
      *((_DWORD *)v9 + 1023) = RtlComputeCrc32(0, Buffer, 0xFFCu);
      v27 = 8 * v3;
      v28 = v4 + 20;
      v10 = HsmpFileCachePreparePinWrite(
              *(PFILE_OBJECT *)(v4[20] + 8 * v3 + 8),
              v20,
              &v23[1],
              (PVOID *)&Buffer,
              (__int64)&v32);
      v22 = v10;
      HsmDbgBreakOnStatus(v10);
      if ( v10 < 0 )
        break;
      LODWORD(v23[0]) = 1;
      memmove(Buffer, v6, 0x1000u);
      v10 = HsmpFileCacheSetAddressRangeModified(Buffer);
      HsmDbgBreakOnStatus(v10);
      if ( v10 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v19 = 87;
LABEL_26:
          WPP_SF_qisdd(v18->AttachedDevice, v19, v11, (_DWORD)v4, *v7, (__int64)(v4 + 4), v3, v10);
        }
        goto LABEL_22;
      }
      v30[0] = *(_OWORD *)v23;
      HsmIBitmapNORMALUnpinBlock(v30);
      LODWORD(v23[0]) = 0;
      Buffer = 0;
      v12 = 0;
      v13 = v27;
      v14 = v28;
      do
      {
        v10 = HsmpFileCacheFlush(*(_QWORD *)(v13 + *v14 + 8));
        LODWORD(v32) = v10;
        HsmDbgBreakOnStatus(v10);
        if ( v10 != -1073741740 )
          break;
        ++v12;
        v10 = -1073741740;
      }
      while ( v12 < 5 );
      v4 = a1;
      v6 = (UCHAR *)P;
      v7 = v26;
      if ( v10 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qisdd(WPP_GLOBAL_Control->AttachedDevice, 88, v32, (_DWORD)a1, *v26, (__int64)(a1 + 4), v3, v32);
        }
        goto LABEL_22;
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
            v15,
            (_DWORD)a1,
            *v26,
            (__int64)(a1 + 4),
            *v29);
        }
        *v33 = v24;
        goto LABEL_14;
      }
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v19 = 85;
      goto LABEL_26;
    }
LABEL_22:
    v10 = HsmiBitmapTranslateIOStatus(v18, (unsigned int)v10);
    v17 = v10;
    goto LABEL_20;
  }
  v10 = -1073741670;
  v17 = -1073741670;
LABEL_20:
  HsmDbgBreakOnStatus(v17);
LABEL_14:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6D427348u);
  if ( LODWORD(v23[0]) )
  {
    v30[0] = *(_OWORD *)v23;
    HsmIBitmapNORMALUnpinBlock(v30);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400720e4  mov     [rsp+arg_10], r8
0x1400720e9  mov     [rsp+arg_0], rcx
0x1400720ee  push    rbx
0x1400720ef  push    rdi
0x1400720f0  push    r12
0x1400720f2  push    r13
0x1400720f4  push    r14
0x1400720f6  push    r15
0x1400720f8  sub     rsp, 0B8h
0x1400720ff  mov     r12d, edx
0x140072102  mov     rdi, rcx
0x140072105  mov     [rsp+0E8h+Buffer], 0
0x14007210e  mov     [rsp+0E8h+var_98], 0
0x140072117  xor     eax, eax
0x140072119  mov     [rsp+0E8h+var_98+8], rax
0x14007211e  mov     edx, 1000h
0x140072123  mov     ecx, 102h
0x140072128  mov     r8d, 6D427348h
0x14007212e  call    cs:__imp_ExAllocatePool2
0x140072135  nop     dword ptr [rax+rax+00h]
0x14007213a  mov     r14, rax
0x14007213d  mov     [rsp+0E8h+P], rax
0x140072142  test    rax, rax
0x140072145  jz      loc_1400723DC
0x14007214b  mov     r15, rdi
0x14007214e  mov     [rsp+0E8h+var_78], rdi
0x140072153  mov     rcx, rax; void *
0x140072156  lea     rax, [rdi+90h]
0x14007215d  mov     [rsp+0E8h+var_58], rax
0x140072165  mov     rax, [rax]
0x140072168  inc     rax
0x14007216b  mov     [rsp+0E8h+var_88], rax
0x140072170  mov     r13d, 2
0x140072176  mov     byte ptr [rsp+0E8h+arg_8], 0
0x14007217e  dec     r12d
0x140072181  mov     [rsp+0E8h+arg_18], r12d
0x140072189  mov     [rsp+0E8h+Buffer], r14
0x14007218e  xor     edx, edx; Val
0x140072190  mov     r8d, 1000h; Size
0x140072196  call    memset
0x14007219b  mov     rax, [rsp+0E8h+Buffer]
0x1400721a0  mov     dword ptr [rax], 704D7442h
0x1400721a6  mov     rax, [rsp+0E8h+Buffer]
0x1400721ab  mov     byte ptr [rax+4], 1
0x1400721af  mov     rax, [rsp+0E8h+Buffer]
0x1400721b4  mov     byte ptr [rax+5], 3
0x1400721b8  mov     rdx, [rsp+0E8h+Buffer]
0x1400721bd  movzx   ecx, byte ptr [rdx+4]
0x1400721c1  shl     cx, 8
0x1400721c5  movzx   eax, byte ptr [rdx+5]
0x1400721c9  or      cx, ax
0x1400721cc  mov     [rdx+6], cx
0x1400721d0  mov     rax, [rsp+0E8h+Buffer]
0x1400721d5  mov     [rax+8], r12d
0x1400721d9  mov     rax, [rsp+0E8h+Buffer]
0x1400721de  mov     rcx, [rsp+0E8h+var_88]
0x1400721e3  mov     [rax+10h], rcx
0x1400721e7  mov     rbx, [rsp+0E8h+Buffer]
0x1400721ec  mov     r8d, 0FFCh; Length
0x1400721f2  mov     rdx, rbx; Buffer
0x1400721f5  xor     ecx, ecx; InitialCrc
0x1400721f7  call    cs:__imp_RtlComputeCrc32
0x1400721fe  nop     dword ptr [rax+rax+00h]
0x140072203  mov     [rbx+0FFCh], eax
0x140072209  lea     r8, ds:0[r12*8]
0x140072211  mov     [rsp+0E8h+var_70], r8
0x140072216  lea     rcx, [rdi+0A0h]
0x14007221d  mov     [rsp+0E8h+var_68], rcx
0x140072225  mov     rax, [rsp+0E8h+Buffer]
0x14007222a  mov     rax, [rax+10h]
0x14007222e  inc     rax
0x140072231  cqo
0x140072233  idiv    r13
0x140072236  shl     rdx, 0Ch
0x14007223a  mov     rcx, [rcx]
0x14007223d  lea     rax, [rsp+0E8h+arg_8]
0x140072245  mov     [rsp+0E8h+var_B0], rax; __int64
0x14007224a  lea     rax, [rsp+0E8h+Buffer]
0x14007224f  mov     [rsp+0E8h+var_B8], rax; PVOID *
0x140072254  lea     rax, [rsp+0E8h+var_98+8]
0x140072259  mov     [rsp+0E8h+var_C0], rax; PVOID *
0x14007225e  mov     r9b, 1
0x140072261  mov     rcx, [rcx+r8+8]; FileObject
0x140072266  call    HsmpFileCachePreparePinWrite
0x14007226b  mov     ebx, eax
0x14007226d  mov     [rsp+0E8h+var_A0], eax
0x140072271  mov     ecx, eax
0x140072273  call    HsmDbgBreakOnStatus
0x140072278  test    ebx, ebx
0x14007227a  js      loc_1400723EA
0x140072280  mov     dword ptr [rsp+0E8h+var_98], 1
0x140072288  mov     r8d, 1000h; Size
0x14007228e  mov     rdx, r14; Src
0x140072291  mov     rcx, [rsp+0E8h+Buffer]; void *
0x140072296  call    memmove
0x14007229b  jmp     short loc_1400722C1
0x14007229d  mov     r13d, 2
0x1400722a3  mov     rdi, [rsp+0E8h+arg_0]
0x1400722ab  mov     ebx, [rsp+0E8h+var_A0]
0x1400722af  mov     r12d, [rsp+0E8h+arg_18]
0x1400722b7  mov     r14, [rsp+0E8h+P]
0x1400722bc  mov     r15, [rsp+0E8h+var_78]
0x1400722c1  test    ebx, ebx
0x1400722c3  js      loc_14007245F
0x1400722c9  mov     rcx, [rsp+0E8h+Buffer]; Address
0x1400722ce  call    HsmpFileCacheSetAddressRangeModified
0x1400722d3  mov     ebx, eax
0x1400722d5  mov     ecx, eax
0x1400722d7  call    HsmDbgBreakOnStatus
0x1400722dc  test    ebx, ebx
0x1400722de  js      loc_14007248A
0x1400722e4  movaps  xmm0, xmmword ptr [rsp+0E8h+var_98]
0x1400722e9  movdqa  [rsp+0E8h+var_48], xmm0
0x1400722f2  lea     rcx, [rsp+0E8h+var_48]
0x1400722fa  call    HsmIBitmapNORMALUnpinBlock
0x1400722ff  mov     dword ptr [rsp+0E8h+var_98], 0
0x140072307  mov     [rsp+0E8h+Buffer], 0
0x140072310  xor     r14d, r14d
0x140072313  mov     r15, [rsp+0E8h+var_70]
0x140072318  mov     rdi, [rsp+0E8h+var_68]
0x140072320  mov     rcx, [rdi]
0x140072323  mov     rcx, [r15+rcx+8]
0x140072328  call    HsmpFileCacheFlush
0x14007232d  mov     ebx, eax
0x14007232f  mov     dword ptr [rsp+0E8h+arg_8], eax
0x140072336  mov     ecx, eax
0x140072338  call    HsmDbgBreakOnStatus
0x14007233d  cmp     ebx, 0C0000054h
0x140072343  jz      loc_1400724BC
0x140072349  test    ebx, ebx
0x14007234b  mov     rdi, [rsp+0E8h+arg_0]
0x140072353  mov     r14, [rsp+0E8h+P]
0x140072358  mov     r15, [rsp+0E8h+var_78]
0x14007235d  js      loc_1400724D3
0x140072363  test    r12d, r12d
0x140072366  mov     rcx, r14
0x140072369  jnz     loc_140072176
0x14007236f  lea     rax, WPP_GLOBAL_Control
0x140072376  mov     rcx, cs:WPP_GLOBAL_Control
0x14007237d  cmp     rcx, rax
0x140072380  jz      short loc_140072393
0x140072382  mov     eax, [rcx+2Ch]
0x140072385  test    al, 1
0x140072387  jz      short loc_140072393
0x140072389  cmp     byte ptr [rcx+29h], 5
0x14007238d  jnb     loc_140072504
0x140072393  mov     rax, [rsp+0E8h+var_88]
0x140072398  mov     rcx, [rsp+0E8h+arg_10]
0x1400723a0  mov     [rcx], rax
0x1400723a3  test    r14, r14
0x1400723a6  jz      short loc_1400723BC
0x1400723a8  mov     edx, 6D427348h; Tag
0x1400723ad  mov     rcx, r14; P
0x1400723b0  call    cs:__imp_ExFreePoolWithTag
0x1400723b7  nop     dword ptr [rax+rax+00h]
0x1400723bc  cmp     dword ptr [rsp+0E8h+var_98], 0
0x1400723c1  jnz     loc_140072536
0x1400723c7  mov     eax, ebx
0x1400723c9  add     rsp, 0B8h
0x1400723d0  pop     r15
0x1400723d2  pop     r14
0x1400723d4  pop     r13
0x1400723d6  pop     r12
0x1400723d8  pop     rdi
0x1400723d9  pop     rbx
0x1400723da  retn
0x1400723dc  mov     ebx, 0C000009Ah
0x1400723e1  mov     ecx, ebx
0x1400723e3  call    HsmDbgBreakOnStatus
0x1400723e8  jmp     short loc_1400723A3
0x1400723ea  lea     rax, WPP_GLOBAL_Control
0x1400723f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723f8  cmp     rcx, rax
0x1400723fb  jnz     short loc_14007240A
0x1400723fd  mov     edx, ebx
0x1400723ff  call    HsmiBitmapTranslateIOStatus
0x140072404  mov     ebx, eax
0x140072406  mov     ecx, eax
0x140072408  jmp     short loc_1400723E3
0x14007240a  mov     eax, [rcx+2Ch]
0x14007240d  test    al, 1
0x14007240f  jz      short loc_1400723FD
0x140072411  cmp     [rcx+29h], r13b
0x140072415  jb      short loc_1400723FD
0x140072417  mov     edx, 55h ; 'U'
0x14007241c  jmp     short loc_140072423
0x14007241e  mov     edx, 57h ; 'W'
0x140072423  mov     dword ptr [rsp+0E8h+var_B0], ebx
0x140072427  jmp     short loc_14007243B
0x140072429  mov     edx, 58h ; 'X'
0x14007242e  mov     r8d, dword ptr [rsp+0E8h+arg_8]
0x140072436  mov     dword ptr [rsp+0E8h+var_B0], r8d
0x14007243b  lea     rax, [rdi+20h]
0x14007243f  mov     dword ptr [rsp+0E8h+var_B8], r12d
0x140072444  mov     [rsp+0E8h+var_C0], rax
0x140072449  mov     rax, [r15]
0x14007244c  mov     [rsp+0E8h+var_C8], rax
0x140072451  mov     r9, rdi
0x140072454  mov     rcx, [rcx+18h]
0x140072458  call    WPP_SF_qisdd
0x14007245d  jmp     short loc_1400723FD
0x14007245f  lea     rax, WPP_GLOBAL_Control
0x140072466  mov     rcx, cs:WPP_GLOBAL_Control
0x14007246d  cmp     rcx, rax
0x140072470  jz      short loc_1400723FD
0x140072472  mov     eax, [rcx+2Ch]
0x140072475  test    al, 1
0x140072477  jz      short loc_1400723FD
0x140072479  cmp     [rcx+29h], r13b
0x14007247d  jb      loc_1400723FD
0x140072483  mov     edx, 56h ; 'V'
0x140072488  jmp     short loc_140072423
0x14007248a  lea     rax, WPP_GLOBAL_Control
0x140072491  mov     rcx, cs:WPP_GLOBAL_Control
0x140072498  cmp     rcx, rax
0x14007249b  jz      loc_1400723FD
0x1400724a1  mov     edx, [rcx+2Ch]
0x1400724a4  test    dl, 1
0x1400724a7  jz      loc_1400723FD
0x1400724ad  cmp     [rcx+29h], r13b
0x1400724b1  jb      loc_1400723FD
0x1400724b7  jmp     loc_14007241E
0x1400724bc  inc     r14d
0x1400724bf  mov     ebx, 0C0000054h
0x1400724c4  cmp     r14d, 5
0x1400724c8  jl      loc_140072320
0x1400724ce  jmp     loc_140072349
0x1400724d3  lea     rax, WPP_GLOBAL_Control
0x1400724da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724e1  cmp     rcx, rax
0x1400724e4  jz      loc_1400723FD
0x1400724ea  mov     eax, [rcx+2Ch]
0x1400724ed  test    al, 1
0x1400724ef  jz      loc_1400723FD
0x1400724f5  cmp     [rcx+29h], r13b
0x1400724f9  jb      loc_1400723FD
0x1400724ff  jmp     loc_140072429
0x140072504  lea     rdx, [rdi+20h]
0x140072508  mov     rax, [rsp+0E8h+var_58]
0x140072510  mov     rax, [rax]
0x140072513  mov     [rsp+0E8h+var_B8], rax
0x140072518  mov     [rsp+0E8h+var_C0], rdx
0x14007251d  mov     rax, [r15]
0x140072520  mov     [rsp+0E8h+var_C8], rax
0x140072525  mov     r9, rdi
0x140072528  mov     rcx, [rcx+18h]
0x14007252c  call    WPP_SF_qisi
0x140072531  jmp     loc_140072393
0x140072536  movaps  xmm0, xmmword ptr [rsp+0E8h+var_98]
0x14007253b  movdqa  [rsp+0E8h+var_48], xmm0
0x140072544  lea     rcx, [rsp+0E8h+var_48]
0x14007254c  call    HsmIBitmapNORMALUnpinBlock
0x140072551  jmp     loc_1400723C7
0x14008696f  push    rbp
0x140086971  sub     rsp, 40h
0x140086975  mov     rbp, rdx
0x140086978  lea     rdx, [rbp+48h]
0x14008697c  call    HsmFileCacheExceptionFilter
0x140086981  nop
0x140086982  add     rsp, 40h
0x140086986  pop     rbp
0x140086987  retn
```
