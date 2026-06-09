# RfcommWriteComplete

- ea: `0x140015c4c`
- end: `0x1400161c8`
- name: `RfcommWriteComplete`
- size: `1404`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ee70`
- `0x140013abc`

## callees

- `0x140003bf4`
- `0x140004684`
- `0x140004a68`
- `0x140004e58`
- `0x140010260`
- `0x140015c4c`
- `0x140019cd0`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015cca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015cca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e54`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016071`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e54`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016071`

## string_xrefs

- `0x140015eeb`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140016041`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x14001608a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140016134`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x14001615b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommWriteComplete(__int64 *a1, int a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // r13
  int v5; // r12d
  volatile __int32 *v6; // rdx
  __int64 v7; // rax
  bool v8; // r15
  __int64 v9; // r14
  _QWORD *v10; // r8
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  KIRQL v13; // al
  _DWORD *v14; // r12
  int v15; // r9d
  int v16; // ecx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  _QWORD *v20; // rcx
  volatile __int32 *v21; // rcx
  volatile __int32 *v22; // rax
  volatile __int32 **v23; // rcx
  __int64 *v24; // rax
  __int64 v25; // rcx
  _QWORD *i; // rdi
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdi
  __int64 result; // rax
  int v32; // edx
  __int128 v33; // [rsp+40h] [rbp-10h] BYREF
  char v34; // [rsp+90h] [rbp+40h]
  int v35; // [rsp+98h] [rbp+48h]

  v35 = a2;
  v2 = *a1;
  v3 = 0;
  v4 = a1[1];
  v34 = 0;
  v5 = a2;
  v33 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      50,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v2);
  *((_QWORD *)&v33 + 1) = &v33;
  *(_QWORD *)&v33 = &v33;
  *(_BYTE *)(v4 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 56));
  v7 = *(_QWORD *)(v2 + 72);
  if ( v7 && *(_DWORD *)(v7 + 16) == 1312901187 )
    v3 = *(_QWORD *)(v2 + 72);
  if ( *(_DWORD *)(v2 + 136) == 1 )
    goto LABEL_50;
  if ( *(_DWORD *)(v2 + 136) == 2 )
    goto LABEL_41;
  if ( *(_DWORD *)(v2 + 136) != 3 )
  {
    if ( *(_DWORD *)(v2 + 136) != 4 )
    {
      if ( *(_DWORD *)(v2 + 136) != 5 )
      {
        v8 = 1;
        goto LABEL_55;
      }
LABEL_41:
      v21 = (volatile __int32 *)(v3 + 168);
      if ( !v3 )
        v21 = (volatile __int32 *)(v4 + 208);
      v22 = *(volatile __int32 **)v21;
      v8 = 0;
      if ( *(volatile __int32 **)v21 != v21 )
      {
        while ( 1 )
        {
          v6 = *(volatile __int32 **)v22;
          if ( v22 == (volatile __int32 *)v2 )
            break;
          v22 = *(volatile __int32 **)v22;
          if ( v6 == v21 )
            goto LABEL_55;
        }
        if ( *((volatile __int32 **)v6 + 1) == v22 )
        {
          v23 = (volatile __int32 **)*((_QWORD *)v22 + 1);
          if ( *v23 == v22 )
          {
            *v23 = v6;
            v8 = 1;
            *((_QWORD *)v6 + 1) = v23;
            *((_QWORD *)v22 + 1) = v22;
            *(_QWORD *)v22 = v22;
            goto LABEL_55;
          }
        }
LABEL_72:
        __fastfail(3u);
      }
      goto LABEL_55;
    }
LABEL_50:
    v8 = 0;
    if ( v5 < 0 )
    {
      if ( v3 )
      {
        v24 = (__int64 *)(v3 + 136);
        v6 = (volatile __int32 *)(v3 + 144);
      }
      else
      {
        v24 = (__int64 *)(v4 + 176);
        v6 = (volatile __int32 *)(v4 + 184);
      }
      v25 = *v24;
      *v24 = 0;
      _InterlockedExchange(v6, 0);
      v8 = v25 == v2;
    }
    goto LABEL_55;
  }
  v9 = *(_QWORD *)(v2 + 80);
  v10 = (_QWORD *)(v3 + 120);
  v11 = *(_QWORD **)(v3 + 120);
  v8 = 0;
  if ( v11 != (_QWORD *)(v3 + 120) )
  {
    while ( 1 )
    {
      v12 = (_QWORD *)*v11;
      if ( v11 == (_QWORD *)v2 )
        break;
      v11 = (_QWORD *)*v11;
      if ( v12 == v10 )
        goto LABEL_19;
    }
    if ( (_QWORD *)v12[1] != v11 )
      goto LABEL_72;
    v6 = (volatile __int32 *)v11[1];
    if ( *(_QWORD **)v6 != v11 )
      goto LABEL_72;
    *(_QWORD *)v6 = v12;
    v8 = 1;
    v12[1] = v6;
    v11[1] = v11;
    *v11 = v11;
  }
LABEL_19:
  if ( v9 )
  {
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 48));
    ++*(_DWORD *)(v9 + 340);
    v14 = (_DWORD *)(v9 + 336);
    v15 = v35;
    v16 = *(_DWORD *)(v9 + 340);
    *(_BYTE *)(v9 + 56) = v13;
    if ( v35 >= 0 )
      *v14 += *(_DWORD *)(v2 + 56);
    v17 = *(_DWORD *)(v2 + 64);
    if ( v16 == v17 )
    {
      v18 = *(_DWORD *)(v2 + 60);
      if ( *v14 == v18 )
        goto LABEL_27;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_Dd(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          1,
          51,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          v18,
          *v14);
        v17 = *(_DWORD *)(v2 + 64);
        v16 = *(_DWORD *)(v9 + 340);
      }
      v15 = -1073741668;
      v35 = -1073741668;
      if ( v16 == v17 )
      {
LABEL_27:
        if ( v15 >= 0 )
          _InterlockedAdd((volatile signed __int32 *)(v9 + 812), *(_DWORD *)(v2 + 60));
        *v14 = 0;
        *(_DWORD *)(v9 + 340) = 0;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 48), *(_BYTE *)(v9 + 56));
    v5 = v35;
    v10 = (_QWORD *)(v3 + 120);
  }
  v19 = *(_DWORD *)(v3 + 48);
  if ( v19 != 5 )
  {
    if ( v19 != 7 )
      goto LABEL_55;
    if ( *(_QWORD *)(v3 + 104) == v3 + 104 && (_QWORD *)*v10 == v10 )
    {
      v34 = 1;
      goto LABEL_55;
    }
  }
  if ( !*(_BYTE *)(v4 + 465) && (*(_BYTE *)(v3 + 208) & 2) == 0 && !*(_BYTE *)(*(_QWORD *)(v3 + 56) + 464LL) )
  {
    ++*(_DWORD *)(v3 + 228);
    v20 = (_QWORD *)*((_QWORD *)&v33 + 1);
    if ( **((__int128 ***)&v33 + 1) == &v33 )
    {
      *(_QWORD *)(v3 + 264) = *((_QWORD *)&v33 + 1);
      *(_QWORD *)(v3 + 256) = &v33;
      *v20 = v3 + 256;
      *((_QWORD *)&v33 + 1) = v3 + 256;
      RefObj_AddRefEx(v3 + 24, 1111705667, 2561, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      goto LABEL_64;
    }
    goto LABEL_72;
  }
LABEL_55:
  for ( i = *(_QWORD **)(v4 + 80); i != (_QWORD *)(v4 + 80); i = (_QWORD *)*i )
  {
    if ( i != (_QWORD *)v3 && (_QWORD *)i[13] != i + 13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v6,
          3,
          52,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          (char)i,
          v3);
      v27 = (_QWORD *)*((_QWORD *)&v33 + 1);
      if ( **((__int128 ***)&v33 + 1) != &v33 )
        goto LABEL_72;
      i[33] = *((_QWORD *)&v33 + 1);
      i[32] = &v33;
      *v27 = i + 32;
      *((_QWORD *)&v33 + 1) = i + 32;
      RefObj_AddRefEx(i + 3, 1111705667, 2579, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
  }
LABEL_64:
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
  if ( v8 )
  {
    *(_DWORD *)(v2 + 104) = v5;
    RefObj_ReleaseEx(v2 + 24, 541803329, 2589, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  while ( 1 )
  {
    v28 = (_QWORD *)v33;
    if ( (__int128 *)v33 == &v33 )
      break;
    if ( *(__int128 **)(v33 + 8) != &v33 )
      goto LABEL_72;
    v29 = *(_QWORD *)v33;
    if ( *(_QWORD *)(*(_QWORD *)v33 + 8LL) != (_QWORD)v33 )
      goto LABEL_72;
    *(_QWORD *)&v33 = *(_QWORD *)v33;
    *(_QWORD *)(v29 + 8) = &v33;
    v30 = (__int64)(v28 - 32);
    v28[1] = v28;
    *v28 = v28;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&v33,
        3,
        53,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        (char)v28,
        v3);
    ChannelSendData(v30);
    RefObj_ReleaseEx(v30 + 24, 1111705667, 2605, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  result = RefObj_ReleaseEx(
             v2 + 24,
             1346917442,
             2611,
             "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( v34 )
    result = ChannelDisconnectRequest(v3, 4);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v32,
             3,
             54,
             (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140015c4c  mov     [rsp-38h+arg_18], rbx
0x140015c51  mov     [rsp-38h+arg_8], edx
0x140015c55  push    rbp
0x140015c56  push    rsi
0x140015c57  push    rdi
0x140015c58  push    r12
0x140015c5a  push    r13
0x140015c5c  push    r14
0x140015c5e  push    r15
0x140015c60  mov     rbp, rsp
0x140015c63  sub     rsp, 50h
0x140015c67  mov     rsi, [rcx]
0x140015c6a  xor     ebx, ebx
0x140015c6c  mov     r13, [rcx+8]
0x140015c70  xorps   xmm0, xmm0
0x140015c73  mov     [rbp+arg_0], bl
0x140015c76  mov     r12d, edx
0x140015c79  movups  [rbp+var_10], xmm0
0x140015c7d  lea     rax, WPP_RECORDER_INITIALIZED
0x140015c84  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015c8b  lea     rcx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015c92  jz      short loc_140015CB6
0x140015c94  mov     [rsp+50h+var_28], rsi
0x140015c99  lea     r9d, [rbx+32h]
0x140015c9d  mov     [rsp+50h+var_30], rcx
0x140015ca2  lea     r8d, [rbx+3]
0x140015ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x140015cad  mov     rcx, [rcx+40h]
0x140015cb1  call    WPP_RECORDER_SF_q
0x140015cb6  lea     rax, [rbp+var_10]
0x140015cba  mov     qword ptr [rbp+var_10+8], rax
0x140015cbe  lea     rcx, [r13+38h]; SpinLock
0x140015cc2  lea     rax, [rbp+var_10]
0x140015cc6  mov     qword ptr [rbp+var_10], rax
0x140015cca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015cd1  nop     dword ptr [rax+rax+00h]
0x140015cd6  mov     [r13+40h], al
0x140015cda  mov     rax, [rsi+48h]
0x140015cde  test    rax, rax
0x140015ce1  jz      short loc_140015CEE
0x140015ce3  cmp     dword ptr [rax+10h], 4E414843h
0x140015cea  cmovz   rbx, rax
0x140015cee  mov     ecx, [rsi+88h]
0x140015cf4  sub     ecx, 1
0x140015cf7  jz      loc_140015F6D
0x140015cfd  sub     ecx, 1
0x140015d00  jz      loc_140015F0C
0x140015d06  sub     ecx, 1
0x140015d09  jz      short loc_140015D28
0x140015d0b  sub     ecx, 1
0x140015d0e  jz      loc_140015F6D
0x140015d14  cmp     ecx, 1
0x140015d17  jz      loc_140015F0C
0x140015d1d  mov     r15d, 1
0x140015d23  jmp     loc_140015FB6
0x140015d28  mov     r14, [rsi+50h]
0x140015d2c  lea     r8, [rbx+78h]
0x140015d30  mov     rax, [r8]
0x140015d33  xor     r15b, r15b
0x140015d36  mov     edi, 1
0x140015d3b  cmp     rax, r8
0x140015d3e  jz      short loc_140015D7A
0x140015d40  mov     rcx, [rax]
0x140015d43  cmp     rax, rsi
0x140015d46  jz      short loc_140015D52
0x140015d48  mov     rax, rcx
0x140015d4b  cmp     rcx, r8
0x140015d4e  jnz     short loc_140015D40
0x140015d50  jmp     short loc_140015D7A
0x140015d52  cmp     [rcx+8], rax
0x140015d56  jnz     loc_14001614B
0x140015d5c  mov     rdx, [rax+8]
0x140015d60  cmp     [rdx], rax
0x140015d63  jnz     loc_14001614B
0x140015d69  mov     [rdx], rcx
0x140015d6c  mov     r15b, dil
0x140015d6f  mov     [rcx+8], rdx
0x140015d73  mov     [rax+8], rax
0x140015d77  mov     [rax], rax
0x140015d7a  test    r14, r14
0x140015d7d  jz      loc_140015E68
0x140015d83  lea     rcx, [r14+30h]; SpinLock
0x140015d87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015d8e  nop     dword ptr [rax+rax+00h]
0x140015d93  add     [r14+154h], edi
0x140015d9a  lea     r12, [r14+150h]
0x140015da1  mov     r9d, [rbp+arg_8]
0x140015da5  mov     ecx, [r14+154h]
0x140015dac  mov     [r14+38h], al
0x140015db0  test    r9d, r9d
0x140015db3  js      short loc_140015DBC
0x140015db5  mov     eax, [rsi+38h]
0x140015db8  add     [r12], eax
0x140015dbc  mov     eax, [rsi+40h]
0x140015dbf  cmp     ecx, eax
0x140015dc1  jnz     loc_140015E4C
0x140015dc7  mov     edx, [rsi+3Ch]
0x140015dca  mov     r8d, [r12]
0x140015dce  cmp     r8d, edx
0x140015dd1  jz      short loc_140015E29
0x140015dd3  lea     r9, WPP_RECORDER_INITIALIZED
0x140015dda  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140015de1  jz      short loc_140015E1B
0x140015de3  mov     rcx, cs:WPP_GLOBAL_Control
0x140015dea  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015df1  mov     dword ptr [rsp+50h+var_20], r8d
0x140015df6  mov     r9d, 33h ; '3'
0x140015dfc  mov     dword ptr [rsp+50h+var_28], edx
0x140015e00  mov     r8d, edi
0x140015e03  mov     [rsp+50h+var_30], rax
0x140015e08  mov     rcx, [rcx+40h]
0x140015e0c  call    WPP_RECORDER_SF_Dd
0x140015e11  mov     eax, [rsi+40h]
0x140015e14  mov     ecx, [r14+154h]
0x140015e1b  mov     r9d, 0C000009Ch
0x140015e21  mov     [rbp+arg_8], r9d
0x140015e25  cmp     ecx, eax
0x140015e27  jnz     short loc_140015E4C
0x140015e29  test    r9d, r9d
0x140015e2c  js      short loc_140015E39
0x140015e2e  mov     eax, [rsi+3Ch]
0x140015e31  lock add [r14+32Ch], eax
0x140015e39  mov     dword ptr [r12], 0
0x140015e41  mov     dword ptr [r14+154h], 0
0x140015e4c  mov     dl, [r14+38h]; NewIrql
0x140015e50  lea     rcx, [r14+30h]; SpinLock
0x140015e54  call    cs:__imp_KeReleaseSpinLock
0x140015e5b  nop     dword ptr [rax+rax+00h]
0x140015e60  mov     r12d, [rbp+arg_8]
0x140015e64  lea     r8, [rbx+78h]
0x140015e68  mov     eax, [rbx+30h]
0x140015e6b  cmp     eax, 5
0x140015e6e  jz      short loc_140015E90
0x140015e70  cmp     eax, 7
0x140015e73  jnz     loc_140015FB6
0x140015e79  lea     rax, [rbx+68h]
0x140015e7d  cmp     [rax], rax
0x140015e80  jnz     short loc_140015E90
0x140015e82  cmp     [r8], r8
0x140015e85  jnz     short loc_140015E90
0x140015e87  mov     [rbp+arg_0], dil
0x140015e8b  jmp     loc_140015FB6
0x140015e90  cmp     byte ptr [r13+1D1h], 0
0x140015e98  jnz     loc_140015FB6
0x140015e9e  test    byte ptr [rbx+0D0h], 2
0x140015ea5  jnz     loc_140015FB6
0x140015eab  mov     rax, [rbx+38h]
0x140015eaf  cmp     byte ptr [rax+1D0h], 0
0x140015eb6  jnz     loc_140015FB6
0x140015ebc  add     [rbx+0E4h], edi
0x140015ec2  lea     rax, [rbp+var_10]
0x140015ec6  mov     rcx, qword ptr [rbp+var_10+8]
0x140015eca  cmp     [rcx], rax
0x140015ecd  jnz     loc_14001614B
0x140015ed3  lea     rax, [rbx+100h]
0x140015eda  mov     r8d, 0A01h
0x140015ee0  mov     [rax+8], rcx
0x140015ee4  lea     rdx, [rbp+var_10]
0x140015ee8  mov     [rax], rdx
0x140015eeb  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140015ef2  mov     [rcx], rax
0x140015ef5  mov     edx, 42434843h
0x140015efa  lea     rcx, [rbx+18h]
0x140015efe  mov     qword ptr [rbp+var_10+8], rax
0x140015f02  call    RefObj_AddRefEx
0x140015f07  jmp     loc_140016069
0x140015f0c  lea     rcx, [rbx+0A8h]
0x140015f13  test    rbx, rbx
0x140015f16  jnz     short loc_140015F1F
0x140015f18  lea     rcx, [r13+0D0h]
0x140015f1f  mov     rax, [rcx]
0x140015f22  xor     r15b, r15b
0x140015f25  cmp     rax, rcx
0x140015f28  jz      loc_140015FB6
0x140015f2e  mov     rdx, [rax]
0x140015f31  cmp     rax, rsi
0x140015f34  jz      short loc_140015F40
0x140015f36  mov     rax, rdx
0x140015f39  cmp     rdx, rcx
0x140015f3c  jnz     short loc_140015F2E
0x140015f3e  jmp     short loc_140015FB6
0x140015f40  cmp     [rdx+8], rax
0x140015f44  jnz     loc_14001614B
0x140015f4a  mov     rcx, [rax+8]
0x140015f4e  cmp     [rcx], rax
0x140015f51  jnz     loc_14001614B
0x140015f57  mov     [rcx], rdx
0x140015f5a  mov     r15d, 1
0x140015f60  mov     [rdx+8], rcx
0x140015f64  mov     [rax+8], rax
0x140015f68  mov     [rax], rax
0x140015f6b  jmp     short loc_140015FB6
0x140015f6d  xor     r15b, r15b
0x140015f70  test    r12d, r12d
0x140015f73  jns     short loc_140015FB6
0x140015f75  test    rbx, rbx
0x140015f78  jz      short loc_140015F8A
0x140015f7a  lea     rax, [rbx+88h]
0x140015f81  lea     rdx, [rbx+90h]
0x140015f88  jmp     short loc_140015F98
0x140015f8a  lea     rax, [r13+0B0h]
0x140015f91  lea     rdx, [r13+0B8h]
0x140015f98  mov     rcx, [rax]
0x140015f9b  mov     edi, 1
0x140015fa0  mov     qword ptr [rax], 0
0x140015fa7  xor     eax, eax
0x140015fa9  xchg    eax, [rdx]
0x140015fab  cmp     rcx, rsi
0x140015fae  movzx   r15d, r15b
0x140015fb2  cmovz   r15d, edi
0x140015fb6  lea     r14, [r13+50h]
0x140015fba  mov     rdi, [r14]
0x140015fbd  jmp     loc_140016060
0x140015fc2  cmp     rdi, rbx
0x140015fc5  jz      loc_14001605D
0x140015fcb  lea     rax, [rdi+68h]
0x140015fcf  cmp     [rax], rax
0x140015fd2  jz      loc_14001605D
0x140015fd8  lea     rax, WPP_RECORDER_INITIALIZED
0x140015fdf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015fe6  jz      short loc_140016018
0x140015fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140015fef  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015ff6  mov     r9d, 34h ; '4'
0x140015ffc  mov     [rsp+50h+var_20], rbx
0x140016001  mov     [rsp+50h+var_28], rdi
0x140016006  mov     [rsp+50h+var_30], rax
0x14001600b  mov     rcx, [rcx+40h]
0x14001600f  lea     r8d, [r9-31h]
0x140016013  call    WPP_RECORDER_SF_qq
0x140016018  mov     rcx, qword ptr [rbp+var_10+8]
0x14001601c  lea     rax, [rbp+var_10]
0x140016020  cmp     [rcx], rax
0x140016023  jnz     loc_14001614B
0x140016029  lea     rax, [rdi+100h]
0x140016030  mov     r8d, 0A13h
0x140016036  mov     [rax+8], rcx
0x14001603a  lea     rdx, [rbp+var_10]
0x14001603e  mov     [rax], rdx
0x140016041  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140016048  mov     [rcx], rax
0x14001604b  mov     edx, 42434843h
0x140016050  lea     rcx, [rdi+18h]
0x140016054  mov     qword ptr [rbp+var_10+8], rax
0x140016058  call    RefObj_AddRefEx
0x14001605d  mov     rdi, [rdi]
0x140016060  cmp     rdi, r14
0x140016063  jnz     loc_140015FC2
0x140016069  mov     dl, [r13+40h]; NewIrql
0x14001606d  lea     rcx, [r13+38h]; SpinLock
0x140016071  call    cs:__imp_KeReleaseSpinLock
0x140016078  nop     dword ptr [rax+rax+00h]
0x14001607d  test    r15b, r15b
0x140016080  jz      short loc_1400160A1
0x140016082  lea     rcx, [rsi+18h]
0x140016086  mov     [rsi+68h], r12d
0x14001608a  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140016091  mov     edx, 204B4341h
0x140016096  mov     r8d, 0A1Dh
0x14001609c  call    RefObj_ReleaseEx
0x1400160a1  lea     r14, WPP_RECORDER_INITIALIZED
0x1400160a8  mov     rax, qword ptr [rbp+var_10]
0x1400160ac  lea     rcx, [rbp+var_10]
0x1400160b0  cmp     rax, rcx
0x1400160b3  jz      loc_140016152
0x1400160b9  lea     rcx, [rbp+var_10]
0x1400160bd  cmp     [rax+8], rcx
0x1400160c1  jnz     loc_14001614B
0x1400160c7  mov     rcx, [rax]
0x1400160ca  cmp     [rcx+8], rax
0x1400160ce  jnz     short loc_14001614B
0x1400160d0  mov     qword ptr [rbp+var_10], rcx
0x1400160d4  lea     rdx, [rbp+var_10]
0x1400160d8  mov     [rcx+8], rdx
0x1400160dc  lea     rdi, [rax-100h]
0x1400160e3  mov     [rax+8], rax
0x1400160e7  mov     [rax], rax
0x1400160ea  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400160f1  jz      short loc_140016123
0x1400160f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400160fa  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140016101  mov     r9d, 35h ; '5'
0x140016107  mov     [rsp+50h+var_20], rbx
0x14001610c  mov     [rsp+50h+var_28], rdi
0x140016111  mov     [rsp+50h+var_30], rax
0x140016116  mov     rcx, [rcx+40h]
0x14001611a  lea     r8d, [r9-32h]
0x14001611e  call    WPP_RECORDER_SF_qq
0x140016123  mov     rcx, rdi
0x140016126  call    ChannelSendData
0x14001612b  lea     rcx, [rdi+18h]
0x14001612f  mov     edx, 42434843h
0x140016134  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001613b  mov     r8d, 0A2Dh
0x140016141  call    RefObj_ReleaseEx
0x140016146  jmp     loc_1400160A8
0x14001614b  mov     ecx, 3
0x140016150  int     29h; Win8: RtlFailFast(ecx)
0x140016152  lea     rcx, [rsi+18h]
0x140016156  mov     edx, 50485442h
  ... truncated ...
```
