# MdaFinishCreate

- ea: `0x1400081f0`
- end: `0x14000866b`
- name: `MdaFinishCreate`
- size: `1147`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400316d0`

## callees

- `0x140008140`
- `0x1400081f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000861b`
- `ntoskrnl!KeReleaseMutex` at `0x14000861b`
- `rdbss!RxFinishFcbInitialization` at `0x14000856a`
- `rdbss!RxFinishFcbInitialization` at `0x14000856a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall MdaFinishCreate(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // r12
  BOOL v6; // edi
  __int64 v7; // rbx
  __int64 v8; // r14
  _DWORD *v9; // r8
  int v10; // eax
  int v11; // ecx
  int v12; // r9d
  int v13; // eax
  unsigned int v14; // edx
  unsigned int i; // ecx
  int v16; // r10d
  unsigned int v17; // eax
  int v18; // r9d
  __int64 v19; // r9
  int v20; // ecx
  unsigned __int16 v21; // di
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  PDEVICE_OBJECT *result; // rax
  __int64 v26; // [rsp+30h] [rbp-49h] BYREF
  __int64 v27; // [rsp+38h] [rbp-41h]
  _FCB_INIT_PACKET InitPacket[2]; // [rsp+40h] [rbp-39h] BYREF
  int v29; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v30; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v32; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = a1[7];
  v4 = a1[10];
  memset(InitPacket, 0, 0x4Cu);
  v6 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v29 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  v7 = *(_QWORD *)(v2 + 136);
  v27 = *(_QWORD *)(a2 + 40);
  v26 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 152LL) + 0x10000LL;
  HacAcquireLock(*(_QWORD *)(v7 + 8));
  if ( !*(_DWORD *)(v2 + 192) )
    *(_QWORD *)(v7 + 16) = 0x4453464E4453464ELL;
  v31 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 196LL) / 0x64u
      + 10000000 * (*(unsigned int *)(*(_QWORD *)(v7 + 8) + 192LL) + 0x2B6109100LL);
  v30 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 204LL) / 0x64u
      + 10000000 * (*(unsigned int *)(*(_QWORD *)(v7 + 8) + 200LL) + 0x2B6109100LL);
  v32 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 212LL) / 0x64u
      + 10000000 * (*(unsigned int *)(*(_QWORD *)(v7 + 8) + 208LL) + 0x2B6109100LL);
  v8 = *(_QWORD *)(v7 + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  v9 = *(_DWORD **)(a2 + 40);
  v10 = *(_DWORD *)(v8 + 140);
  v11 = v9[9];
  if ( v11 == v10 || (_WORD)v11 == (_WORD)v10 )
  {
    v6 = *(_BYTE *)(v8 + 132) >= 0;
  }
  else
  {
    v12 = *(_DWORD *)(v8 + 144);
    v13 = v9[10];
    if ( v13 == v12 || (_WORD)v13 == (_WORD)v12 )
    {
      v6 = (*(_DWORD *)(v8 + 132) & 0x10) == 0;
    }
    else
    {
      v14 = v9[11];
      for ( i = 0; i < v14; ++i )
      {
        v16 = v9[i + 12];
        if ( v16 == v12 || (_WORD)v16 == (_WORD)v12 )
        {
          if ( (*(_DWORD *)(v8 + 132) & 0x10) == 0 )
            v6 = 1;
          goto LABEL_25;
        }
      }
      if ( i == v14 && (*(_DWORD *)(v8 + 132) & 2) == 0 )
        v6 = 1;
    }
  }
LABEL_25:
  v17 = *(_DWORD *)(v8 + 128);
  if ( v17 == 2 )
  {
    v18 = 16;
  }
  else if ( v17 == 5 || v17 <= 2 || v17 >= 8 )
  {
    v18 = 32;
  }
  else
  {
    v18 = 4;
  }
  v19 = v6 | (unsigned int)v18;
  v29 = v19;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_cca3db0522623f5e31396e1525c29988_Traceguids, v19, v19);
  v20 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 128LL);
  if ( ((v20 - 1) & 0xFFFFFFFB) != 0 && v20 == 2 )
    v21 = -5087;
  else
    v21 = -5086;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v21);
  LODWORD(InitPacket[0].pAttributes) = 0;
  InitPacket[0].pNumLinks = (PULONG)&v29;
  InitPacket[0].pCreationTime = (PLARGE_INTEGER)(*(_QWORD *)(v7 + 8) + 136LL);
  InitPacket[0].pLastAccessTime = (PLARGE_INTEGER)&v30;
  InitPacket[0].pLastWriteTime = (PLARGE_INTEGER)&v31;
  InitPacket[0].pLastChangeTime = (PLARGE_INTEGER)&v30;
  InitPacket[0].pAllocationSize = (PLARGE_INTEGER)&v32;
  InitPacket[0].pFileSize = (PLARGE_INTEGER)&v26;
  InitPacket[0].pValidDataLength = (PLARGE_INTEGER)(*(_QWORD *)(v7 + 8) + 152LL);
  InitPacket[1].pAttributes = (PULONG)(*(_QWORD *)(v7 + 8) + 152LL);
  if ( *(_DWORD *)(v2 + 192) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  }
  else
  {
    RxFinishFcbInitialization((PMRX_FCB)v2, (RX_FILE_TYPE)v21, InitPacket);
  }
  v22 = a1[9];
  v23 = v27;
  *(_QWORD *)(v22 + 112) = 0;
  *(_QWORD *)(v22 + 104) = 0;
  if ( (*(_DWORD *)(v4 + 2316) & 0x40) != 0 || (*(_DWORD *)(v23 + 32) & 1) != 0 || (*(_DWORD *)(v7 + 28) & 1) != 0 )
  {
    a1[92] = 0;
    *(_DWORD *)(v7 + 28) |= 1u;
  }
  else
  {
    *((_DWORD *)a1 + 184) = 11;
  }
  v24 = *(_DWORD *)(v23 + 32);
  if ( (v24 & 0x80u) == 0 && (v24 & 0x100) != 0 )
  {
    if ( v21 == 0xEC22 )
      *((_DWORD *)a1 + 184) &= 0xFFFFFFCF;
  }
  else
  {
    *(_DWORD *)(v22 + 72) |= 0x80u;
  }
  ++*(_DWORD *)(*(_QWORD *)(v7 + 8) + 56LL);
  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v7 + 8) + 40LL), 0);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 8) != 0 )
      return (PDEVICE_OBJECT *)WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 98,
                                 WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1400081f0  push    rbp
0x1400081f2  push    rbx
0x1400081f3  push    rsi
0x1400081f4  push    rdi
0x1400081f5  push    r12
0x1400081f7  push    r13
0x1400081f9  push    r14
0x1400081fb  push    r15
0x1400081fd  lea     rbp, [rsp-1Fh]
0x140008202  sub     rsp, 98h
0x140008209  mov     r15, [rcx+38h]
0x14000820d  mov     r13, rdx
0x140008210  mov     r12, [rcx+50h]
0x140008214  mov     rsi, rcx
0x140008217  xor     eax, eax
0x140008219  lea     rcx, [rbp+57h+InitPacket]; void *
0x14000821d  xor     edx, edx; Val
0x14000821f  mov     dword ptr [rbp+57h+InitPacket.pAttributes+4], eax
0x140008222  mov     r8d, 4Ch ; 'L'; Size
0x140008228  call    memset
0x14000822d  xor     edi, edi
0x14000822f  mov     [rbp+57h+arg_10], rdi
0x140008233  mov     [rbp+57h+arg_8], rdi
0x140008237  mov     [rbp+57h+arg_18], rdi
0x14000823b  mov     [rbp+57h+arg_0], edi
0x14000823e  mov     [rbp+57h+var_A0], rdi
0x140008242  mov     rcx, cs:WPP_GLOBAL_Control
0x140008249  lea     rax, WPP_GLOBAL_Control
0x140008250  cmp     rcx, rax
0x140008253  jz      short loc_140008271
0x140008255  mov     eax, [rcx+2Ch]
0x140008258  test    al, 8
0x14000825a  jz      short loc_140008271
0x14000825c  mov     rcx, [rcx+18h]
0x140008260  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140008267  mov     edx, 5Fh ; '_'
0x14000826c  call    WPP_SF_
0x140008271  mov     rbx, [r15+88h]
0x140008278  mov     rax, [r13+28h]
0x14000827c  mov     [rbp+57h+var_98], rax
0x140008280  mov     rax, [rbx+8]
0x140008284  mov     rcx, [rax+98h]
0x14000828b  add     rcx, 10000h
0x140008292  mov     [rbp+57h+var_A0], rcx
0x140008296  mov     rcx, [rbx+8]
0x14000829a  call    HacAcquireLock
0x14000829f  cmp     [r15+0C0h], edi
0x1400082a6  jnz     short loc_1400082B6
0x1400082a8  mov     rax, 4453464E4453464Eh
0x1400082b2  mov     [rbx+10h], rax
0x1400082b6  mov     rdx, [rbx+8]
0x1400082ba  mov     r9, 2B6109100h
0x1400082c4  mov     eax, [rdx+0C0h]
0x1400082ca  add     rax, r9
0x1400082cd  imul    rcx, rax, 989680h
0x1400082d4  mov     eax, 51EB851Fh
0x1400082d9  mul     dword ptr [rdx+0C4h]
0x1400082df  shr     edx, 5
0x1400082e2  mov     eax, edx
0x1400082e4  add     rcx, rax
0x1400082e7  mov     eax, 51EB851Fh
0x1400082ec  mov     [rbp+57h+arg_10], rcx
0x1400082f0  mov     rdx, [rbx+8]
0x1400082f4  mov     ecx, [rdx+0C8h]
0x1400082fa  mul     dword ptr [rdx+0CCh]
0x140008300  add     rcx, r9
0x140008303  mov     eax, 51EB851Fh
0x140008308  imul    r8, rcx, 989680h
0x14000830f  shr     edx, 5
0x140008312  mov     ecx, edx
0x140008314  add     r8, rcx
0x140008317  mov     [rbp+57h+arg_8], r8
0x14000831b  mov     rdx, [rbx+8]
0x14000831f  mov     ecx, [rdx+0D0h]
0x140008325  mul     dword ptr [rdx+0D4h]
0x14000832b  add     rcx, r9
0x14000832e  shr     edx, 5
0x140008331  imul    r8, rcx, 989680h
0x140008338  mov     eax, edx
0x14000833a  add     r8, rax
0x14000833d  mov     [rbp+57h+arg_18], r8
0x140008341  mov     r14, [rbx+8]
0x140008345  mov     rcx, cs:WPP_GLOBAL_Control
0x14000834c  lea     rdx, WPP_GLOBAL_Control
0x140008353  cmp     rcx, rdx
0x140008356  jz      short loc_14000837B
0x140008358  mov     eax, [rcx+2Ch]
0x14000835b  test    al, 8
0x14000835d  jz      short loc_14000837B
0x14000835f  mov     rcx, [rcx+18h]
0x140008363  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14000836a  mov     edx, 15h
0x14000836f  call    WPP_SF_
0x140008374  lea     rdx, WPP_GLOBAL_Control
0x14000837b  mov     r8, [r13+28h]
0x14000837f  mov     eax, [r14+8Ch]
0x140008386  mov     ecx, [r8+24h]
0x14000838a  cmp     ecx, eax
0x14000838c  jz      loc_140008416
0x140008392  cmp     cx, ax
0x140008395  jz      short loc_140008416
0x140008397  mov     r9d, [r14+90h]
0x14000839e  mov     eax, [r8+28h]
0x1400083a2  cmp     eax, r9d
0x1400083a5  jz      short loc_140008405
0x1400083a7  cmp     ax, r9w
0x1400083ab  jz      short loc_140008405
0x1400083ad  mov     edx, [r8+2Ch]
0x1400083b1  xor     r13d, r13d
0x1400083b4  mov     ecx, r13d
0x1400083b7  cmp     ecx, edx
0x1400083b9  jnb     short loc_1400083EA
0x1400083bb  mov     eax, ecx
0x1400083bd  mov     r10d, [r8+rax*4+30h]
0x1400083c2  cmp     r10d, r9d
0x1400083c5  jz      short loc_1400083D1
0x1400083c7  cmp     r10w, r9w
0x1400083cb  jz      short loc_1400083D1
0x1400083cd  inc     ecx
0x1400083cf  jmp     short loc_1400083B7
0x1400083d1  mov     eax, [r14+84h]
0x1400083d8  lea     rdx, WPP_GLOBAL_Control
0x1400083df  test    al, 10h
0x1400083e1  jnz     short loc_14000842D
0x1400083e3  mov     edi, 1
0x1400083e8  jmp     short loc_14000842D
0x1400083ea  lea     rdx, WPP_GLOBAL_Control
0x1400083f1  jnz     short loc_14000842D
0x1400083f3  mov     eax, [r14+84h]
0x1400083fa  test    al, 2
0x1400083fc  jnz     short loc_14000842D
0x1400083fe  mov     edi, 1
0x140008403  jmp     short loc_14000842D
0x140008405  mov     edi, [r14+84h]
0x14000840c  shr     edi, 4
0x14000840f  not     edi
0x140008411  and     edi, 1
0x140008414  jmp     short loc_14000842A
0x140008416  test    byte ptr [r14+84h], 80h
0x14000841e  mov     eax, edi
0x140008420  mov     edi, 1
0x140008425  cmovz   eax, edi
0x140008428  mov     edi, eax
0x14000842a  xor     r13d, r13d
0x14000842d  mov     eax, [r14+80h]
0x140008434  cmp     eax, 2
0x140008437  jnz     short loc_140008441
0x140008439  mov     r9d, 10h
0x14000843f  jmp     short loc_14000845E
0x140008441  cmp     eax, 5
0x140008444  jz      short loc_140008458
0x140008446  cmp     eax, 2
0x140008449  jbe     short loc_140008458
0x14000844b  cmp     eax, 8
0x14000844e  jnb     short loc_140008458
0x140008450  mov     r9d, 4
0x140008456  jmp     short loc_14000845E
0x140008458  mov     r9d, 20h ; ' '
0x14000845e  or      r9d, edi
0x140008461  mov     [rbp+57h+arg_0], r9d
0x140008465  mov     rcx, cs:WPP_GLOBAL_Control
0x14000846c  cmp     rcx, rdx
0x14000846f  jz      short loc_140008499
0x140008471  mov     eax, [rcx+2Ch]
0x140008474  test    al, 8
0x140008476  jz      short loc_140008499
0x140008478  mov     rcx, [rcx+18h]
0x14000847c  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140008483  mov     edx, 16h
0x140008488  mov     [rsp+0D0h+var_B0], r9d
0x14000848d  call    WPP_SF_dd
0x140008492  lea     rdx, WPP_GLOBAL_Control
0x140008499  mov     rax, [rbx+8]
0x14000849d  mov     r14d, 0EC22h
0x1400084a3  mov     ecx, [rax+80h]
0x1400084a9  lea     eax, [rcx-1]
0x1400084ac  test    eax, 0FFFFFFFBh
0x1400084b1  jz      short loc_1400084BF
0x1400084b3  cmp     ecx, 2
0x1400084b6  jnz     short loc_1400084BF
0x1400084b8  mov     edi, 0EC21h
0x1400084bd  jmp     short loc_1400084C3
0x1400084bf  movzx   edi, r14w
0x1400084c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084ca  cmp     rcx, rdx
0x1400084cd  jz      short loc_1400084F8
0x1400084cf  test    dword ptr [rcx+2Ch], 100h
0x1400084d6  jz      short loc_1400084F8
0x1400084d8  mov     rcx, [rcx+18h]
0x1400084dc  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400084e3  movzx   r9d, di
0x1400084e7  mov     edx, 60h ; '`'
0x1400084ec  call    WPP_SF_d
0x1400084f1  lea     rdx, WPP_GLOBAL_Control
0x1400084f8  mov     dword ptr [rbp+57h+InitPacket.pAttributes], r13d
0x1400084fc  lea     rax, [rbp+57h+arg_0]
0x140008500  mov     [rbp+57h+InitPacket.pNumLinks], rax
0x140008504  mov     rax, [rbx+8]
0x140008508  add     rax, 88h
0x14000850e  mov     [rbp+57h+InitPacket.pCreationTime], rax
0x140008512  lea     rax, [rbp+57h+arg_8]
0x140008516  mov     [rbp+57h+InitPacket.pLastAccessTime], rax
0x14000851a  lea     rax, [rbp+57h+arg_10]
0x14000851e  mov     [rbp+57h+InitPacket.pLastWriteTime], rax
0x140008522  lea     rax, [rbp+57h+arg_8]
0x140008526  mov     [rbp+57h+InitPacket.pLastChangeTime], rax
0x14000852a  lea     rax, [rbp+57h+arg_18]
0x14000852e  mov     [rbp+57h+InitPacket.pAllocationSize], rax
0x140008532  lea     rax, [rbp+57h+var_A0]
0x140008536  mov     [rbp+57h+InitPacket.pFileSize], rax
0x14000853a  mov     rax, [rbx+8]
0x14000853e  add     rax, 98h
0x140008544  mov     [rbp+57h+InitPacket.pValidDataLength], rax
0x140008548  mov     rax, [rbx+8]
0x14000854c  add     rax, 98h
0x140008552  mov     [rbp+57h+var_48], rax
0x140008556  cmp     dword ptr [r15+0C0h], 0
0x14000855e  jnz     short loc_140008578
0x140008560  movzx   edx, di; FileType
0x140008563  lea     r8, [rbp+57h+InitPacket]; InitPacket
0x140008567  mov     rcx, r15; Fcb
0x14000856a  call    cs:__imp_RxFinishFcbInitialization
0x140008571  nop     dword ptr [rax+rax+00h]
0x140008576  jmp     short loc_1400085A2
0x140008578  mov     rcx, cs:WPP_GLOBAL_Control
0x14000857f  cmp     rcx, rdx
0x140008582  jz      short loc_1400085A2
0x140008584  test    dword ptr [rcx+2Ch], 100h
0x14000858b  jz      short loc_1400085A2
0x14000858d  mov     rcx, [rcx+18h]
0x140008591  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140008598  mov     edx, 61h ; 'a'
0x14000859d  call    WPP_SF_
0x1400085a2  mov     rcx, [rsi+48h]
0x1400085a6  mov     rdx, [rbp+57h+var_98]
0x1400085aa  mov     [rcx+70h], r13
0x1400085ae  mov     [rcx+68h], r13
0x1400085b2  mov     eax, [r12+90Ch]
0x1400085ba  test    al, 40h
0x1400085bc  jnz     short loc_1400085D8
0x1400085be  mov     eax, [rdx+20h]
0x1400085c1  test    al, 1
0x1400085c3  jnz     short loc_1400085D8
0x1400085c5  mov     eax, [rbx+1Ch]
0x1400085c8  test    al, 1
0x1400085ca  jnz     short loc_1400085D8
0x1400085cc  mov     dword ptr [rsi+2E0h], 0Bh
0x1400085d6  jmp     short loc_1400085E7
0x1400085d8  mov     qword ptr [rsi+2E0h], 0
0x1400085e3  or      dword ptr [rbx+1Ch], 1
0x1400085e7  mov     eax, [rdx+20h]
0x1400085ea  test    al, al
0x1400085ec  js      short loc_140008603
0x1400085ee  bt      eax, 8
0x1400085f2  jnb     short loc_140008603
0x1400085f4  cmp     di, r14w
0x1400085f8  jnz     short loc_14000860A
0x1400085fa  and     dword ptr [rsi+2E0h], 0FFFFFFCFh
0x140008601  jmp     short loc_14000860A
0x140008603  or      dword ptr [rcx+48h], 80h
0x14000860a  mov     rax, [rbx+8]
0x14000860e  xor     edx, edx; Wait
0x140008610  inc     dword ptr [rax+38h]
0x140008613  mov     rcx, [rbx+8]
0x140008617  mov     rcx, [rcx+28h]; Mutex
0x14000861b  call    cs:__imp_KeReleaseMutex
0x140008622  nop     dword ptr [rax+rax+00h]
0x140008627  mov     rcx, cs:WPP_GLOBAL_Control
0x14000862e  lea     rax, WPP_GLOBAL_Control
0x140008635  cmp     rcx, rax
0x140008638  jz      short loc_140008656
0x14000863a  mov     eax, [rcx+2Ch]
0x14000863d  test    al, 8
0x14000863f  jz      short loc_140008656
0x140008641  mov     rcx, [rcx+18h]
0x140008645  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14000864c  mov     edx, 62h ; 'b'
0x140008651  call    WPP_SF_
0x140008656  add     rsp, 98h
0x14000865d  pop     r15
0x14000865f  pop     r14
0x140008661  pop     r13
0x140008663  pop     r12
0x140008665  pop     rdi
0x140008666  pop     rsi
0x140008667  pop     rbx
0x140008668  pop     rbp
0x140008669  retn
```
