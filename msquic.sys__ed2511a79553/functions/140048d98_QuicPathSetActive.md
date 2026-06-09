# QuicPathSetActive

- ea: `0x140048d98`
- end: `0x140049048`
- name: `QuicPathSetActive`
- size: `688`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140013200`
- `0x14002b5c4`

## callees

- `0x14003c8e0`
- `0x14003c980`
- `0x14003ec10`
- `0x140048d98`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140048fef`
- `ntoskrnl!_snprintf_s` at `0x140048fef`

## string_xrefs

- `0x140048fd0`: `Path[%hhu] Set active (rebind=%hhu)`

## pseudocode

```c
void __fastcall QuicPathSetActive(__int64 a1, __int64 a2)
{
  unsigned __int8 v2; // di
  unsigned __int8 *v3; // r8
  __int16 v5; // ax
  bool v6; // zf
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  char v21; // cl
  char v22; // al
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  _OWORD *v30; // rdx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int64 v37; // rcx
  __int128 DstBuf; // [rsp+30h] [rbp-108h] BYREF
  __int128 v39; // [rsp+40h] [rbp-F8h]
  __int128 v40; // [rsp+50h] [rbp-E8h]
  __int128 v41; // [rsp+60h] [rbp-D8h]
  __int128 v42; // [rsp+70h] [rbp-C8h]
  __int128 v43; // [rsp+80h] [rbp-B8h]
  __int128 v44; // [rsp+90h] [rbp-A8h]
  __int128 v45; // [rsp+A0h] [rbp-98h]
  __int128 v46; // [rsp+B0h] [rbp-88h]
  __int128 v47; // [rsp+C0h] [rbp-78h]
  __int128 v48; // [rsp+D0h] [rbp-68h]
  __int128 v49; // [rsp+E0h] [rbp-58h]
  __int128 v50; // [rsp+F0h] [rbp-48h]
  __int128 v51; // [rsp+100h] [rbp-38h]
  __int128 v52; // [rsp+110h] [rbp-28h]

  v2 = 0;
  v3 = (unsigned __int8 *)(a1 + 320);
  if ( a2 == a1 + 320 )
  {
    *(_BYTE *)(a2 + 1) |= 2u;
    goto LABEL_13;
  }
  v5 = *(_WORD *)(a2 + 56);
  if ( v5 == *(_WORD *)(a1 + 376) )
  {
    if ( v5 == 2 )
    {
      v6 = *(_DWORD *)(a2 + 60) == *(_DWORD *)(a1 + 380);
      goto LABEL_8;
    }
    if ( *(_QWORD *)(a2 + 64) == *(_QWORD *)(a1 + 384) )
    {
      v6 = *(_QWORD *)(a2 + 72) == *(_QWORD *)(a1 + 392);
LABEL_8:
      if ( v6 )
        v2 = 1;
    }
  }
  v7 = *(_OWORD *)(a1 + 336);
  DstBuf = *(_OWORD *)v3;
  v8 = *(_OWORD *)(a1 + 352);
  v39 = v7;
  v9 = *(_OWORD *)(a1 + 368);
  v40 = v8;
  v10 = *(_OWORD *)(a1 + 384);
  v41 = v9;
  v11 = *(_OWORD *)(a1 + 400);
  v42 = v10;
  v12 = *(_OWORD *)(a1 + 416);
  v43 = v11;
  v13 = *(_OWORD *)(a1 + 432);
  v44 = v12;
  v14 = *(_OWORD *)(a1 + 448);
  v45 = v13;
  v15 = *(_OWORD *)(a1 + 464);
  v46 = v14;
  v16 = *(_OWORD *)(a1 + 480);
  v47 = v15;
  v17 = *(_OWORD *)(a1 + 496);
  v48 = v16;
  v18 = *(_OWORD *)(a1 + 512);
  v49 = v17;
  v19 = *(_OWORD *)(a1 + 528);
  v50 = v18;
  v20 = *(_OWORD *)(a1 + 544);
  v51 = v19;
  v52 = v20;
  v21 = *(_BYTE *)(a2 + 1) | 2;
  v22 = BYTE1(DstBuf) & 0xFD;
  *(_BYTE *)(a2 + 1) = v21;
  BYTE1(DstBuf) = v22;
  if ( v2 )
    *(_BYTE *)(a2 + 1) = v21 ^ (v21 ^ v22) & 0x40;
  *(_OWORD *)v3 = *(_OWORD *)a2;
  *((_OWORD *)v3 + 1) = *(_OWORD *)(a2 + 16);
  *((_OWORD *)v3 + 2) = *(_OWORD *)(a2 + 32);
  *((_OWORD *)v3 + 3) = *(_OWORD *)(a2 + 48);
  *((_OWORD *)v3 + 4) = *(_OWORD *)(a2 + 64);
  *((_OWORD *)v3 + 5) = *(_OWORD *)(a2 + 80);
  *((_OWORD *)v3 + 6) = *(_OWORD *)(a2 + 96);
  *((_OWORD *)v3 + 7) = *(_OWORD *)(a2 + 112);
  *((_OWORD *)v3 + 8) = *(_OWORD *)(a2 + 128);
  *((_OWORD *)v3 + 9) = *(_OWORD *)(a2 + 144);
  *((_OWORD *)v3 + 10) = *(_OWORD *)(a2 + 160);
  *((_OWORD *)v3 + 11) = *(_OWORD *)(a2 + 176);
  *((_OWORD *)v3 + 12) = *(_OWORD *)(a2 + 192);
  *((_OWORD *)v3 + 13) = *(_OWORD *)(a2 + 208);
  v23 = v39;
  *((_OWORD *)v3 + 14) = *(_OWORD *)(a2 + 224);
  *(_OWORD *)a2 = DstBuf;
  v24 = v40;
  *(_OWORD *)(a2 + 16) = v23;
  v25 = v41;
  *(_OWORD *)(a2 + 32) = v24;
  v26 = v42;
  *(_OWORD *)(a2 + 48) = v25;
  v27 = v43;
  *(_OWORD *)(a2 + 64) = v26;
  v28 = v44;
  *(_OWORD *)(a2 + 80) = v27;
  v29 = v45;
  *(_OWORD *)(a2 + 96) = v28;
  v30 = (_OWORD *)(a2 + 128);
  *(v30 - 1) = v29;
  v31 = v47;
  *v30 = v46;
  v32 = v48;
  v30[1] = v31;
  v33 = v49;
  v30[2] = v32;
  v34 = v50;
  v30[3] = v33;
  v35 = v51;
  v30[4] = v34;
  v36 = v52;
  v30[5] = v35;
  v30[6] = v36;
LABEL_13:
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s((char *)&DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] Set active (rebind=%hhu)", *v3, v2);
    McTemplateU0ps_EtwWriteTransfer(v37, QuicConnLogInfo, a1, &DstBuf);
  }
  if ( !v2 )
    (*(void (__fastcall **)(__int64, _QWORD))(a1 + 2192))(a1 + 2168, 0);
}

```

## disassembly

```asm
0x140048d98  mov     [rsp+arg_10], rbx
0x140048d9d  push    rdi
0x140048d9e  sub     rsp, 130h
0x140048da5  mov     rax, cs:__security_cookie
0x140048dac  xor     rax, rsp
0x140048daf  mov     [rsp+138h+var_18], rax
0x140048db7  xor     dil, dil
0x140048dba  lea     r8, [rcx+140h]
0x140048dc1  mov     rbx, rcx
0x140048dc4  mov     r10d, 80h
0x140048dca  cmp     rdx, r8
0x140048dcd  jnz     short loc_140048DD8
0x140048dcf  or      byte ptr [rdx+1], 2
0x140048dd3  jmp     loc_140048FC3
0x140048dd8  movzx   eax, word ptr [rdx+38h]
0x140048ddc  cmp     ax, [rcx+178h]
0x140048de3  jnz     short loc_140048E13
0x140048de5  cmp     ax, 2
0x140048de9  jnz     short loc_140048DF6
0x140048deb  mov     eax, [rdx+3Ch]
0x140048dee  cmp     eax, [rcx+17Ch]
0x140048df4  jmp     short loc_140048E0E
0x140048df6  mov     rax, [rdx+40h]
0x140048dfa  cmp     rax, [rcx+180h]
0x140048e01  jnz     short loc_140048E13
0x140048e03  mov     rax, [rdx+48h]
0x140048e07  cmp     rax, [rcx+188h]
0x140048e0e  jnz     short loc_140048E13
0x140048e10  mov     dil, 1
0x140048e13  movups  xmm0, xmmword ptr [r8]
0x140048e17  lea     rcx, [rsp+138h+DstBuf]
0x140048e1c  movups  xmm1, xmmword ptr [r8+10h]
0x140048e21  lea     rax, [r10+r8]
0x140048e25  movups  xmmword ptr [rcx], xmm0
0x140048e28  movups  xmm0, xmmword ptr [r8+20h]
0x140048e2d  movups  xmmword ptr [rcx+10h], xmm1
0x140048e31  movups  xmm1, xmmword ptr [r8+30h]
0x140048e36  movups  xmmword ptr [rcx+20h], xmm0
0x140048e3a  movups  xmm0, xmmword ptr [r8+40h]
0x140048e3f  movups  xmmword ptr [rcx+30h], xmm1
0x140048e43  movups  xmm1, xmmword ptr [r8+50h]
0x140048e48  movups  xmmword ptr [rcx+40h], xmm0
0x140048e4c  movups  xmm0, xmmword ptr [r8+60h]
0x140048e51  movups  xmmword ptr [rcx+50h], xmm1
0x140048e55  movups  xmm1, xmmword ptr [r8+70h]
0x140048e5a  movups  xmmword ptr [rcx+60h], xmm0
0x140048e5e  add     rcx, r10
0x140048e61  movups  xmm0, xmmword ptr [rax]
0x140048e64  movups  xmmword ptr [rcx-10h], xmm1
0x140048e68  movups  xmm1, xmmword ptr [rax+10h]
0x140048e6c  movups  xmmword ptr [rcx], xmm0
0x140048e6f  movups  xmm0, xmmword ptr [rax+20h]
0x140048e73  movups  xmmword ptr [rcx+10h], xmm1
0x140048e77  movups  xmm1, xmmword ptr [rax+30h]
0x140048e7b  movups  xmmword ptr [rcx+20h], xmm0
0x140048e7f  movups  xmm0, xmmword ptr [rax+40h]
0x140048e83  movups  xmmword ptr [rcx+30h], xmm1
0x140048e87  movups  xmm1, xmmword ptr [rax+50h]
0x140048e8b  movups  xmmword ptr [rcx+40h], xmm0
0x140048e8f  movups  xmm0, xmmword ptr [rax+60h]
0x140048e93  movups  xmmword ptr [rcx+50h], xmm1
0x140048e97  movups  xmmword ptr [rcx+60h], xmm0
0x140048e9b  mov     rax, qword ptr [rsp+138h+DstBuf]
0x140048ea0  mov     cl, [rdx+1]
0x140048ea3  shr     rax, 8
0x140048ea7  or      cl, 2
0x140048eaa  and     al, 0FDh
0x140048eac  mov     [rdx+1], cl
0x140048eaf  mov     byte ptr [rsp+138h+DstBuf+1], al
0x140048eb3  test    dil, dil
0x140048eb6  jz      short loc_140048EC1
0x140048eb8  xor     al, cl
0x140048eba  and     al, 40h
0x140048ebc  xor     al, cl
0x140048ebe  mov     [rdx+1], al
0x140048ec1  movups  xmm0, xmmword ptr [rdx]
0x140048ec4  lea     rax, [r10+rdx]
0x140048ec8  lea     rcx, [r10+r8]
0x140048ecc  movups  xmmword ptr [r8], xmm0
0x140048ed0  movups  xmm1, xmmword ptr [rdx+10h]
0x140048ed4  movups  xmmword ptr [r8+10h], xmm1
0x140048ed9  movups  xmm0, xmmword ptr [rdx+20h]
0x140048edd  movups  xmmword ptr [r8+20h], xmm0
0x140048ee2  movups  xmm1, xmmword ptr [rdx+30h]
0x140048ee6  movups  xmmword ptr [r8+30h], xmm1
0x140048eeb  movups  xmm0, xmmword ptr [rdx+40h]
0x140048eef  movups  xmmword ptr [r8+40h], xmm0
0x140048ef4  movups  xmm1, xmmword ptr [rdx+50h]
0x140048ef8  movups  xmmword ptr [r8+50h], xmm1
0x140048efd  movups  xmm0, xmmword ptr [rdx+60h]
0x140048f01  movups  xmmword ptr [r8+60h], xmm0
0x140048f06  movups  xmm1, xmmword ptr [rdx+70h]
0x140048f0a  movups  xmmword ptr [rcx-10h], xmm1
0x140048f0e  movups  xmm0, xmmword ptr [rax]
0x140048f11  movups  xmmword ptr [rcx], xmm0
0x140048f14  movups  xmm1, xmmword ptr [rax+10h]
0x140048f18  movups  xmmword ptr [rcx+10h], xmm1
0x140048f1c  movups  xmm0, xmmword ptr [rax+20h]
0x140048f20  movups  xmmword ptr [rcx+20h], xmm0
0x140048f24  movups  xmm1, xmmword ptr [rax+30h]
0x140048f28  movups  xmmword ptr [rcx+30h], xmm1
0x140048f2c  movups  xmm0, xmmword ptr [rax+40h]
0x140048f30  movups  xmmword ptr [rcx+40h], xmm0
0x140048f34  movups  xmm1, xmmword ptr [rax+50h]
0x140048f38  movups  xmmword ptr [rcx+50h], xmm1
0x140048f3c  movups  xmm0, xmmword ptr [rax+60h]
0x140048f40  lea     rax, [rsp+138h+DstBuf]
0x140048f45  movups  xmm1, xmmword ptr [rax+10h]
0x140048f49  movups  xmmword ptr [rcx+60h], xmm0
0x140048f4d  movups  xmm0, xmmword ptr [rax]
0x140048f50  movups  xmmword ptr [rdx], xmm0
0x140048f53  movups  xmm0, xmmword ptr [rax+20h]
0x140048f57  movups  xmmword ptr [rdx+10h], xmm1
0x140048f5b  movups  xmm1, xmmword ptr [rax+30h]
0x140048f5f  movups  xmmword ptr [rdx+20h], xmm0
0x140048f63  movups  xmm0, xmmword ptr [rax+40h]
0x140048f67  movups  xmmword ptr [rdx+30h], xmm1
0x140048f6b  movups  xmm1, xmmword ptr [rax+50h]
0x140048f6f  movups  xmmword ptr [rdx+40h], xmm0
0x140048f73  movups  xmm0, xmmword ptr [rax+60h]
0x140048f77  movups  xmmword ptr [rdx+50h], xmm1
0x140048f7b  movups  xmm1, xmmword ptr [rax+70h]
0x140048f7f  movups  xmmword ptr [rdx+60h], xmm0
0x140048f83  add     rdx, r10
0x140048f86  add     rax, r10
0x140048f89  movups  xmmword ptr [rdx-10h], xmm1
0x140048f8d  movups  xmm0, xmmword ptr [rax]
0x140048f90  movups  xmm1, xmmword ptr [rax+10h]
0x140048f94  movups  xmmword ptr [rdx], xmm0
0x140048f97  movups  xmm0, xmmword ptr [rax+20h]
0x140048f9b  movups  xmmword ptr [rdx+10h], xmm1
0x140048f9f  movups  xmm1, xmmword ptr [rax+30h]
0x140048fa3  movups  xmmword ptr [rdx+20h], xmm0
0x140048fa7  movups  xmm0, xmmword ptr [rax+40h]
0x140048fab  movups  xmmword ptr [rdx+30h], xmm1
0x140048faf  movups  xmm1, xmmword ptr [rax+50h]
0x140048fb3  movups  xmmword ptr [rdx+40h], xmm0
0x140048fb7  movups  xmm0, xmmword ptr [rax+60h]
0x140048fbb  movups  xmmword ptr [rdx+50h], xmm1
0x140048fbf  movups  xmmword ptr [rdx+60h], xmm0
0x140048fc3  test    cs:byte_14005C48B, r10b
0x140048fca  jz      short loc_14004900F
0x140048fcc  movzx   ecx, byte ptr [r8]
0x140048fd0  lea     r9, aPathHhuSetActi; "Path[%hhu] Set active (rebind=%hhu)"
0x140048fd7  movzx   eax, dil
0x140048fdb  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140048fdf  mov     [rsp+138h+var_110], eax
0x140048fe3  mov     rdx, r10; SizeInBytes
0x140048fe6  mov     [rsp+138h+var_118], ecx
0x140048fea  lea     rcx, [rsp+138h+DstBuf]; DstBuf
0x140048fef  call    cs:__imp__snprintf_s
0x140048ff6  nop     dword ptr [rax+rax+00h]
0x140048ffb  lea     r9, [rsp+138h+DstBuf]
0x140049000  mov     r8, rbx
0x140049003  lea     rdx, QuicConnLogInfo
0x14004900a  call    McTemplateU0ps_EtwWriteTransfer
0x14004900f  test    dil, dil
0x140049012  jnz     short loc_140049026
0x140049014  lea     rcx, [rbx+878h]
0x14004901b  xor     edx, edx
0x14004901d  mov     rax, [rcx+18h]
0x140049021  call    _guard_dispatch_icall
0x140049026  mov     rcx, [rsp+138h+var_18]
0x14004902e  xor     rcx, rsp; StackCookie
0x140049031  call    __security_check_cookie
0x140049036  mov     rbx, [rsp+138h+arg_10]
0x14004903e  add     rsp, 130h
0x140049045  pop     rdi
0x140049046  retn
```
