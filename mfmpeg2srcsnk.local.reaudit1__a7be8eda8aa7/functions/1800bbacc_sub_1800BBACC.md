# sub_1800BBACC

- ea: `0x1800bbacc`
- end: `0x1800bbfcc`
- name: `sub_1800BBACC`
- size: `1280`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18003f5e0`
- `0x1800487b8`
- `0x1800b4ad8`

## callees

- `0x180006960`
- `0x18000ac80`
- `0x18000c470`
- `0x18000e400`
- `0x1800251f0`
- `0x18002d790`
- `0x180037a98`
- `0x1800a9030`
- `0x1800b0804`
- `0x1800b5f08`
- `0x1800b9b00`
- `0x1800bbacc`
- `0x1800bccd8`
- `0x1800fcf10`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbcb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbe20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbeea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbcb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbe20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbeea`
- `MFPlat!MFCreateMediaEvent` at `0x1800bbbbd`
- `MFPlat!MFCreateMediaEvent` at `0x1800bbbbd`

## string_xrefs

- `0x1800bbadf`: `CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics`

## pseudocode

```c
__int64 __fastcall sub_1800BBACC(__int64 a1, int a2)
{
  __int64 v4; // rcx
  int v5; // r9d
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // esi
  int v9; // r9d
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r8
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  char v39; // [rsp+60h] [rbp+8h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+70h] [rbp+18h] BYREF

  sub_180006960(&v39, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2772);
  v5 = *(_DWORD *)(a1 + 1080);
  v6 = *(unsigned int *)(a1 + 1160);
  v7 = v5 & 0xFFFFFF75;
  ppEvent = 0;
  if ( (v6 & 4) != 0 && (unsigned int)sub_1800B9B00(a1, v6, v7) )
    v7 = (unsigned int)v7 | 2;
  if ( (v7 & 2) != 0 && (v6 & 0x100) != 0 && !*(_DWORD *)(a1 + 1164) )
    v7 = (unsigned int)v7 | 8;
  v8 = v7 | 0x80;
  if ( (v6 & 0x800) == 0 )
    v8 = v7;
  if ( v5 == v8 )
  {
LABEL_60:
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 920) + 48LL))(
            *(_QWORD *)(a1 + 920),
            a1 + 1040,
            a1 + 1048);
    if ( v11 >= 0 )
    {
      if ( (unsigned __int8)sub_1800B5F08(v33, v32, v34) >= 0x10u )
        sub_1800BCCD8(
          *((_QWORD *)RequestContext + 17),
          264,
          &stru_180111EA0,
          a1,
          *(_QWORD *)(a1 + 1040),
          *(_QWORD *)(a1 + 1048));
    }
    else
    {
      v35 = (__int64 *)qword_18012EC10;
      if ( !qword_18012EC10 )
      {
        v36 = MFGetCallStackTracingWeakReference(0, v32);
        qword_18012EC10 = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v35 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = sub_18000C470(v35);
        if ( *(_DWORD *)(v37 + 1996) != v11 )
          sub_18000E400(v37, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2829, (unsigned int)v11);
      }
      if ( (unsigned __int8)sub_1800A9030(v35, v32, v34) )
      {
        v16 = 263;
        goto LABEL_25;
      }
    }
    goto LABEL_73;
  }
  if ( (unsigned __int8)sub_1800B5F08(v4, v6, v7) >= 8u )
    sub_1800B0804(*((_QWORD *)RequestContext + 17), 258, &stru_180111EA0, a1, v9, v8);
  if ( !a2 )
  {
LABEL_59:
    *(_DWORD *)(a1 + 1080) = v8;
    goto LABEL_60;
  }
  v11 = MFCreateMediaEvent(0xDBu, &Buf2, 0, 0, &ppEvent);
  if ( v11 < 0 )
  {
    v13 = (__int64 *)qword_18012EC10;
    if ( !qword_18012EC10 )
    {
      v14 = MFGetCallStackTracingWeakReference(0, v10);
      qword_18012EC10 = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)qword_18012EC10;
      }
      else
      {
        v13 = &qword_18012E0B0;
        qword_18012EC10 = (__int64)&qword_18012E0B0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = sub_18000C470(v13);
      if ( *(_DWORD *)(v15 + 1996) != v11 )
        sub_18000E400(v15, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2815, (unsigned int)v11);
    }
    if ( (unsigned __int8)sub_1800A9030(v13, v10, v12) )
    {
      v16 = 259;
LABEL_25:
      sub_180037A98(*((_QWORD *)RequestContext + 2), v16, &stru_180111EA0, a1, v11);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  v11 = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
          ppEvent,
          qword_18010F0A0,
          v8);
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
            ppEvent,
            qword_18010F0B0,
            *(unsigned int *)(a1 + 1080));
    if ( v11 < 0 )
    {
      v24 = (__int64 *)qword_18012EC10;
      if ( !qword_18012EC10 )
      {
        v25 = MFGetCallStackTracingWeakReference(0, v22);
        qword_18012EC10 = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v24 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = sub_18000C470(v24);
        if ( *(_DWORD *)(v26 + 1996) != v11 )
          sub_18000E400(v26, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2818, (unsigned int)v11);
      }
      if ( (unsigned __int8)sub_1800A9030(v24, v22, v23) )
      {
        v16 = 261;
        goto LABEL_25;
      }
      goto LABEL_73;
    }
    v11 = sub_1800251F0(a1 + 768, (__int64)ppEvent);
    if ( v11 < 0 )
    {
      v29 = (__int64 *)qword_18012EC10;
      if ( !qword_18012EC10 )
      {
        v30 = MFGetCallStackTracingWeakReference(0, v27);
        qword_18012EC10 = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v29 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = sub_18000C470(v29);
        if ( *(_DWORD *)(v31 + 1996) != v11 )
          sub_18000E400(v31, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2820, (unsigned int)v11);
      }
      if ( (unsigned __int8)sub_1800A9030(v29, v27, v28) )
      {
        v16 = 262;
        goto LABEL_25;
      }
      goto LABEL_73;
    }
    goto LABEL_59;
  }
  v19 = (__int64 *)qword_18012EC10;
  if ( !qword_18012EC10 )
  {
    v20 = MFGetCallStackTracingWeakReference(0, v17);
    qword_18012EC10 = v20;
    if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
    {
      v19 = (__int64 *)qword_18012EC10;
    }
    else
    {
      v19 = &qword_18012E0B0;
      qword_18012EC10 = (__int64)&qword_18012E0B0;
    }
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v21 = sub_18000C470(v19);
    if ( *(_DWORD *)(v21 + 1996) != v11 )
      sub_18000E400(v21, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2817, (unsigned int)v11);
  }
  if ( (unsigned __int8)sub_1800A9030(v19, v17, v18) )
  {
    v16 = 260;
    goto LABEL_25;
  }
LABEL_73:
  sub_18002D790(&ppEvent);
  sub_18000AC80(&v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800bbacc  mov     [rsp+arg_8], rbx
0x1800bbad1  push    rsi
0x1800bbad2  push    rdi
0x1800bbad3  push    r12
0x1800bbad5  push    r14
0x1800bbad7  push    r15
0x1800bbad9  sub     rsp, 30h
0x1800bbadd  mov     ebx, edx
0x1800bbadf  lea     r12, aCmfbytestreamm_86; "CMFByteStreamMediaSource::UpdateMediaSo"...
0x1800bbae6  mov     rdi, rcx
0x1800bbae9  mov     rdx, r12
0x1800bbaec  mov     r8d, 0AD4h
0x1800bbaf2  lea     rcx, [rsp+58h+arg_0]
0x1800bbaf7  call    sub_180006960
0x1800bbafc  mov     r9d, [rdi+438h]
0x1800bbb03  mov     r8d, r9d
0x1800bbb06  mov     edx, [rdi+488h]
0x1800bbb0c  and     r8d, 0FFFFFF75h
0x1800bbb13  mov     [rsp+58h+arg_10], 0
0x1800bbb1c  test    dl, 4
0x1800bbb1f  jz      short loc_1800BBB31
0x1800bbb21  mov     rcx, rdi
0x1800bbb24  call    sub_1800B9B00
0x1800bbb29  test    eax, eax
0x1800bbb2b  jz      short loc_1800BBB31
0x1800bbb2d  or      r8d, 2
0x1800bbb31  test    r8b, 2
0x1800bbb35  jz      short loc_1800BBB4A
0x1800bbb37  bt      edx, 8
0x1800bbb3b  jnb     short loc_1800BBB4A
0x1800bbb3d  cmp     dword ptr [rdi+48Ch], 0
0x1800bbb44  jnz     short loc_1800BBB4A
0x1800bbb46  or      r8d, 8
0x1800bbb4a  mov     esi, r8d
0x1800bbb4d  lea     r15, stru_180111EA0
0x1800bbb54  bts     esi, 7
0x1800bbb58  bt      edx, 0Bh
0x1800bbb5c  cmovnb  esi, r8d
0x1800bbb60  cmp     r9d, esi
0x1800bbb63  jz      loc_1800BBEAC
0x1800bbb69  call    sub_1800B5F08
0x1800bbb6e  cmp     al, 8
0x1800bbb70  jb      short loc_1800BBB99
0x1800bbb72  mov     rcx, cs:RequestContext
0x1800bbb79  mov     edx, 102h
0x1800bbb7e  mov     dword ptr [rsp+58h+var_30], esi
0x1800bbb82  mov     r8, r15
0x1800bbb85  mov     dword ptr [rsp+58h+ppEvent], r9d
0x1800bbb8a  mov     r9, rdi
0x1800bbb8d  mov     rcx, [rcx+88h]
0x1800bbb94  call    sub_1800B0804
0x1800bbb99  test    ebx, ebx
0x1800bbb9b  jz      loc_1800BBEA6
0x1800bbba1  lea     rax, [rsp+58h+arg_10]
0x1800bbba6  xor     r9d, r9d; pvValue
0x1800bbba9  xor     r8d, r8d; hrStatus
0x1800bbbac  mov     [rsp+58h+ppEvent], rax; ppEvent
0x1800bbbb1  lea     rdx, Buf2; guidExtendedType
0x1800bbbb8  mov     ecx, 0DBh; met
0x1800bbbbd  call    cs:MFCreateMediaEvent
0x1800bbbc4  nop     dword ptr [rax+rax+00h]
0x1800bbbc9  mov     ebx, eax
0x1800bbbcb  test    eax, eax
0x1800bbbcd  jns     loc_1800BBC7F
0x1800bbbd3  mov     rcx, cs:qword_18012EC10
0x1800bbbda  test    rcx, rcx
0x1800bbbdd  jnz     short loc_1800BBC27
0x1800bbbdf  call    cs:MFGetCallStackTracingWeakReference
0x1800bbbe6  nop     dword ptr [rax+rax+00h]
0x1800bbbeb  mov     cs:qword_18012EC10, rax
0x1800bbbf2  mov     rcx, rax
0x1800bbbf5  test    rax, rax
0x1800bbbf8  jz      short loc_1800BBC19
0x1800bbbfa  mov     rax, [rax]
0x1800bbbfd  mov     edx, 7F0h
0x1800bbc02  mov     rax, [rax+8]
0x1800bbc06  call    cs:__guard_dispatch_icall_fptr
0x1800bbc0c  test    eax, eax
0x1800bbc0e  jz      short loc_1800BBC19
0x1800bbc10  mov     rcx, cs:qword_18012EC10
0x1800bbc17  jmp     short loc_1800BBC27
0x1800bbc19  lea     rcx, qword_18012E0B0
0x1800bbc20  mov     cs:qword_18012EC10, rcx
0x1800bbc27  cmp     byte ptr [rcx+8], 0
0x1800bbc2b  jz      short loc_1800BBC4E
0x1800bbc2d  call    sub_18000C470
0x1800bbc32  cmp     [rax+7CCh], ebx
0x1800bbc38  jz      short loc_1800BBC4E
0x1800bbc3a  mov     r9d, ebx
0x1800bbc3d  mov     r8d, 0AFFh
0x1800bbc43  mov     rdx, r12
0x1800bbc46  mov     rcx, rax
0x1800bbc49  call    sub_18000E400
0x1800bbc4e  call    sub_1800A9030
0x1800bbc53  cmp     al, 1
0x1800bbc55  jb      loc_1800BBFA3
0x1800bbc5b  mov     edx, 103h
0x1800bbc60  mov     rcx, cs:RequestContext
0x1800bbc67  mov     r9, rdi
0x1800bbc6a  mov     r8, r15
0x1800bbc6d  mov     dword ptr [rsp+58h+ppEvent], ebx
0x1800bbc71  mov     rcx, [rcx+10h]
0x1800bbc75  call    sub_180037A98
0x1800bbc7a  jmp     loc_1800BBFA3
0x1800bbc7f  mov     rcx, [rsp+58h+arg_10]
0x1800bbc84  lea     rdx, qword_18010F0A0
0x1800bbc8b  mov     r8d, esi
0x1800bbc8e  mov     rax, [rcx]
0x1800bbc91  mov     rax, [rax+0A8h]
0x1800bbc98  call    cs:__guard_dispatch_icall_fptr
0x1800bbc9e  mov     ebx, eax
0x1800bbca0  test    eax, eax
0x1800bbca2  jns     loc_1800BBD3A
0x1800bbca8  mov     rcx, cs:qword_18012EC10
0x1800bbcaf  test    rcx, rcx
0x1800bbcb2  jnz     short loc_1800BBCFC
0x1800bbcb4  call    cs:MFGetCallStackTracingWeakReference
0x1800bbcbb  nop     dword ptr [rax+rax+00h]
0x1800bbcc0  mov     cs:qword_18012EC10, rax
0x1800bbcc7  mov     rcx, rax
0x1800bbcca  test    rax, rax
0x1800bbccd  jz      short loc_1800BBCEE
0x1800bbccf  mov     rax, [rax]
0x1800bbcd2  mov     edx, 7F0h
0x1800bbcd7  mov     rax, [rax+8]
0x1800bbcdb  call    cs:__guard_dispatch_icall_fptr
0x1800bbce1  test    eax, eax
0x1800bbce3  jz      short loc_1800BBCEE
0x1800bbce5  mov     rcx, cs:qword_18012EC10
0x1800bbcec  jmp     short loc_1800BBCFC
0x1800bbcee  lea     rcx, qword_18012E0B0
0x1800bbcf5  mov     cs:qword_18012EC10, rcx
0x1800bbcfc  cmp     byte ptr [rcx+8], 0
0x1800bbd00  jz      short loc_1800BBD23
0x1800bbd02  call    sub_18000C470
0x1800bbd07  cmp     [rax+7CCh], ebx
0x1800bbd0d  jz      short loc_1800BBD23
0x1800bbd0f  mov     r9d, ebx
0x1800bbd12  mov     r8d, 0B01h
0x1800bbd18  mov     rdx, r12
0x1800bbd1b  mov     rcx, rax
0x1800bbd1e  call    sub_18000E400
0x1800bbd23  call    sub_1800A9030
0x1800bbd28  cmp     al, 1
0x1800bbd2a  jb      loc_1800BBFA3
0x1800bbd30  mov     edx, 104h
0x1800bbd35  jmp     loc_1800BBC60
0x1800bbd3a  mov     rcx, [rsp+58h+arg_10]
0x1800bbd3f  lea     rdx, qword_18010F0B0
0x1800bbd46  mov     r8d, [rdi+438h]
0x1800bbd4d  mov     rax, [rcx]
0x1800bbd50  mov     rax, [rax+0A8h]
0x1800bbd57  call    cs:__guard_dispatch_icall_fptr
0x1800bbd5d  mov     ebx, eax
0x1800bbd5f  test    eax, eax
0x1800bbd61  jns     loc_1800BBDF9
0x1800bbd67  mov     rcx, cs:qword_18012EC10
0x1800bbd6e  test    rcx, rcx
0x1800bbd71  jnz     short loc_1800BBDBB
0x1800bbd73  call    cs:MFGetCallStackTracingWeakReference
0x1800bbd7a  nop     dword ptr [rax+rax+00h]
0x1800bbd7f  mov     cs:qword_18012EC10, rax
0x1800bbd86  mov     rcx, rax
0x1800bbd89  test    rax, rax
0x1800bbd8c  jz      short loc_1800BBDAD
0x1800bbd8e  mov     rax, [rax]
0x1800bbd91  mov     edx, 7F0h
0x1800bbd96  mov     rax, [rax+8]
0x1800bbd9a  call    cs:__guard_dispatch_icall_fptr
0x1800bbda0  test    eax, eax
0x1800bbda2  jz      short loc_1800BBDAD
0x1800bbda4  mov     rcx, cs:qword_18012EC10
0x1800bbdab  jmp     short loc_1800BBDBB
0x1800bbdad  lea     rcx, qword_18012E0B0
0x1800bbdb4  mov     cs:qword_18012EC10, rcx
0x1800bbdbb  cmp     byte ptr [rcx+8], 0
0x1800bbdbf  jz      short loc_1800BBDE2
0x1800bbdc1  call    sub_18000C470
0x1800bbdc6  cmp     [rax+7CCh], ebx
0x1800bbdcc  jz      short loc_1800BBDE2
0x1800bbdce  mov     r9d, ebx
0x1800bbdd1  mov     r8d, 0B02h
0x1800bbdd7  mov     rdx, r12
0x1800bbdda  mov     rcx, rax
0x1800bbddd  call    sub_18000E400
0x1800bbde2  call    sub_1800A9030
0x1800bbde7  cmp     al, 1
0x1800bbde9  jb      loc_1800BBFA3
0x1800bbdef  mov     edx, 105h
0x1800bbdf4  jmp     loc_1800BBC60
0x1800bbdf9  mov     rdx, [rsp+58h+arg_10]
0x1800bbdfe  lea     rcx, [rdi+300h]
0x1800bbe05  call    sub_1800251F0
0x1800bbe0a  mov     ebx, eax
0x1800bbe0c  test    eax, eax
0x1800bbe0e  jns     loc_1800BBEA6
0x1800bbe14  mov     rcx, cs:qword_18012EC10
0x1800bbe1b  test    rcx, rcx
0x1800bbe1e  jnz     short loc_1800BBE68
0x1800bbe20  call    cs:MFGetCallStackTracingWeakReference
0x1800bbe27  nop     dword ptr [rax+rax+00h]
0x1800bbe2c  mov     cs:qword_18012EC10, rax
0x1800bbe33  mov     rcx, rax
0x1800bbe36  test    rax, rax
0x1800bbe39  jz      short loc_1800BBE5A
0x1800bbe3b  mov     rax, [rax]
0x1800bbe3e  mov     edx, 7F0h
0x1800bbe43  mov     rax, [rax+8]
0x1800bbe47  call    cs:__guard_dispatch_icall_fptr
0x1800bbe4d  test    eax, eax
0x1800bbe4f  jz      short loc_1800BBE5A
0x1800bbe51  mov     rcx, cs:qword_18012EC10
0x1800bbe58  jmp     short loc_1800BBE68
0x1800bbe5a  lea     rcx, qword_18012E0B0
0x1800bbe61  mov     cs:qword_18012EC10, rcx
0x1800bbe68  cmp     byte ptr [rcx+8], 0
0x1800bbe6c  jz      short loc_1800BBE8F
0x1800bbe6e  call    sub_18000C470
0x1800bbe73  cmp     [rax+7CCh], ebx
0x1800bbe79  jz      short loc_1800BBE8F
0x1800bbe7b  mov     r9d, ebx
0x1800bbe7e  mov     r8d, 0B04h
0x1800bbe84  mov     rdx, r12
0x1800bbe87  mov     rcx, rax
0x1800bbe8a  call    sub_18000E400
0x1800bbe8f  call    sub_1800A9030
0x1800bbe94  cmp     al, 1
0x1800bbe96  jb      loc_1800BBFA3
0x1800bbe9c  mov     edx, 106h
0x1800bbea1  jmp     loc_1800BBC60
0x1800bbea6  mov     [rdi+438h], esi
0x1800bbeac  mov     rcx, [rdi+398h]
0x1800bbeb3  lea     rsi, [rdi+418h]
0x1800bbeba  lea     r14, [rdi+410h]
0x1800bbec1  mov     r8, rsi
0x1800bbec4  mov     rdx, r14
0x1800bbec7  mov     rax, [rcx]
0x1800bbeca  mov     rax, [rax+30h]
0x1800bbece  call    cs:__guard_dispatch_icall_fptr
0x1800bbed4  mov     ebx, eax
0x1800bbed6  test    eax, eax
0x1800bbed8  jns     loc_1800BBF6C
0x1800bbede  mov     rcx, cs:qword_18012EC10
0x1800bbee5  test    rcx, rcx
0x1800bbee8  jnz     short loc_1800BBF32
0x1800bbeea  call    cs:MFGetCallStackTracingWeakReference
0x1800bbef1  nop     dword ptr [rax+rax+00h]
0x1800bbef6  mov     cs:qword_18012EC10, rax
0x1800bbefd  mov     rcx, rax
0x1800bbf00  test    rax, rax
0x1800bbf03  jz      short loc_1800BBF24
0x1800bbf05  mov     rax, [rax]
0x1800bbf08  mov     edx, 7F0h
0x1800bbf0d  mov     rax, [rax+8]
0x1800bbf11  call    cs:__guard_dispatch_icall_fptr
0x1800bbf17  test    eax, eax
0x1800bbf19  jz      short loc_1800BBF24
0x1800bbf1b  mov     rcx, cs:qword_18012EC10
0x1800bbf22  jmp     short loc_1800BBF32
0x1800bbf24  lea     rcx, qword_18012E0B0
0x1800bbf2b  mov     cs:qword_18012EC10, rcx
0x1800bbf32  cmp     byte ptr [rcx+8], 0
0x1800bbf36  jz      short loc_1800BBF59
0x1800bbf38  call    sub_18000C470
0x1800bbf3d  cmp     [rax+7CCh], ebx
0x1800bbf43  jz      short loc_1800BBF59
0x1800bbf45  mov     r9d, ebx
0x1800bbf48  mov     r8d, 0B0Dh
0x1800bbf4e  mov     rdx, r12
0x1800bbf51  mov     rcx, rax
0x1800bbf54  call    sub_18000E400
0x1800bbf59  call    sub_1800A9030
0x1800bbf5e  cmp     al, 1
0x1800bbf60  jb      short loc_1800BBFA3
0x1800bbf62  mov     edx, 107h
0x1800bbf67  jmp     loc_1800BBC60
0x1800bbf6c  call    sub_1800B5F08
0x1800bbf71  cmp     al, 10h
0x1800bbf73  jb      short loc_1800BBFA3
0x1800bbf75  mov     rcx, [r14]
0x1800bbf78  mov     edx, 108h
0x1800bbf7d  mov     rax, [rsi]
0x1800bbf80  mov     r9, rdi
0x1800bbf83  mov     [rsp+58h+var_30], rax
0x1800bbf88  mov     r8, r15
0x1800bbf8b  mov     [rsp+58h+ppEvent], rcx
0x1800bbf90  mov     rcx, cs:RequestContext
0x1800bbf97  mov     rcx, [rcx+88h]
0x1800bbf9e  call    sub_1800BCCD8
0x1800bbfa3  lea     rcx, [rsp+58h+arg_10]
0x1800bbfa8  call    sub_18002D790
0x1800bbfad  lea     rcx, [rsp+58h+arg_0]
0x1800bbfb2  call    sub_18000AC80
0x1800bbfb7  mov     eax, ebx
0x1800bbfb9  mov     rbx, [rsp+58h+arg_8]
0x1800bbfbe  add     rsp, 30h
0x1800bbfc2  pop     r15
0x1800bbfc4  pop     r14
0x1800bbfc6  pop     r12
0x1800bbfc8  pop     rdi
  ... truncated ...
```
