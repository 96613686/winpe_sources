# CDSBaseUpdate::InitProperty(BufferReader *,ulong,tagPROPVARIANT &)

- ea: `0x180014c50`
- end: `0x180015135`
- name: `?InitProperty@CDSBaseUpdate@@AEAAJPEAVBufferReader@@KAEAUtagPROPVARIANT@@@Z`
- size: `1253`
- prototype: `__int64 __fastcall(CDSBaseUpdate *__hidden this, struct BufferReader *, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014730`

## callees

- `0x180014c50`
- `0x18001513c`
- `0x1800151d0`
- `0x18001722c`

## pseudocode

```c
__int64 __fastcall CDSBaseUpdate::InitProperty(
        CDSBaseUpdate *this,
        struct BufferReader *a2,
        unsigned int a3,
        struct tagPROPVARIANT *a4)
{
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned __int64 LowPart; // r8
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  LARGE_INTEGER *v22; // rsi
  BYTE *v23; // rax
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  LARGE_INTEGER *p_hVal; // r14
  LARGE_INTEGER *v28; // rdx
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  bool v32; // zf
  unsigned int v33; // r8d
  unsigned int v34; // r8d
  unsigned int v35; // r8d
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  unsigned int v38; // r8d
  unsigned int v39; // r8d
  unsigned int v41; // r8d
  unsigned int v42; // r8d
  unsigned int v43; // r8d
  unsigned int v44; // r8d
  unsigned int v45; // r8d
  unsigned int v46; // r8d
  unsigned int v47; // r8d
  unsigned int v48; // r8d
  unsigned int v49; // r8d
  unsigned int v50; // r8d
  unsigned int v51; // r8d
  unsigned int v52; // r8d
  unsigned int v53; // r8d
  unsigned int v54; // r8d
  unsigned int v55; // r8d
  unsigned int v56; // r8d
  unsigned int v57; // r8d
  unsigned int v58; // r8d
  unsigned int v59; // r8d
  unsigned int v60; // r8d
  unsigned int v61; // r8d
  unsigned int v62; // r8d
  unsigned int v63; // r8d
  unsigned int v64; // r8d
  unsigned int v65; // r8d
  unsigned int v66; // r8d
  unsigned int v67; // r8d
  unsigned int v68; // r8d
  unsigned int v69; // r8d
  unsigned int v70; // r8d
  unsigned int v71; // r8d
  unsigned int v72; // r8d

  *(_OWORD *)&a4->vt = 0;
  a4->bstrblobVal.pData = 0;
  if ( a3 > 0xC9 )
  {
    if ( a3 <= 0x12D )
    {
      if ( a3 == 301 )
        goto LABEL_74;
      if ( a3 > 0xD6 )
      {
        v33 = a3 - 215;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( !v34 )
            goto LABEL_74;
          v35 = v34 - 1;
          if ( !v35 )
            goto LABEL_14;
          v36 = v35 - 1;
          if ( !v36 )
            goto LABEL_14;
          v37 = v36 - 1;
          if ( v37 )
          {
            v38 = v37 - 1;
            if ( !v38 )
              goto LABEL_88;
            v39 = v38 - 7;
            if ( v39 && v39 - 1 > 1 )
              return 3222142977LL;
          }
LABEL_52:
          a4->vt = 17;
          LowPart = 1;
          goto LABEL_53;
        }
        goto LABEL_88;
      }
      if ( a3 == 214 )
        goto LABEL_88;
      if ( a3 <= 0xD1 )
      {
        if ( a3 != 209 )
        {
          v24 = a3 - 202;
          if ( !v24 )
            goto LABEL_82;
          v25 = v24 - 1;
          if ( !v25 )
            goto LABEL_74;
          v26 = v25 - 3;
          if ( !v26 )
            goto LABEL_24;
          if ( v26 - 1 > 1 )
            return 3222142977LL;
        }
LABEL_36:
        p_hVal = &a4->hVal;
        a4->vt = 4168;
        BufferReader::ReadBytes(a2, &a4->decVal.8, 4u);
        if ( p_hVal->LowPart )
        {
          v23 = (BYTE *)MmAllocate(saturated_mul(p_hVal->LowPart, 0x10u));
          LowPart = 16LL * p_hVal->LowPart;
          goto LABEL_38;
        }
LABEL_119:
        a4->bstrblobVal.pData = 0;
        return 0;
      }
      v29 = a3 - 210;
      if ( !v29 )
        goto LABEL_88;
      v30 = v29 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_88;
LABEL_43:
        v32 = v31 == 1;
        goto LABEL_117;
      }
LABEL_82:
      a4->vt = 72;
      v23 = (BYTE *)MmAllocate(0x10u);
      a4->hVal.QuadPart = (LONGLONG)v23;
      LowPart = 16;
      goto LABEL_39;
    }
    if ( a3 > 0x268 )
    {
      if ( a3 > 0x44D )
      {
        if ( a3 > 0x57A )
        {
          v69 = a3 - 1403;
          if ( !v69 )
            goto LABEL_52;
          v70 = v69 - 1;
          if ( !v70 )
            goto LABEL_52;
          v71 = v70 - 1;
          if ( !v71 )
            goto LABEL_82;
          v72 = v71 - 96;
          if ( !v72 )
          {
LABEL_24:
            v22 = &a4->hVal;
            a4->vt = 65;
            BufferReader::ReadBytes(a2, &a4->decVal.8, 4u);
            if ( v22->LowPart )
            {
              v23 = (BYTE *)MmAllocate(v22->LowPart);
              LowPart = v22->LowPart;
LABEL_38:
              a4->bstrblobVal.pData = v23;
LABEL_39:
              v28 = (LARGE_INTEGER *)v23;
LABEL_54:
              BufferReader::ReadBytes(a2, v28, LowPart);
              return 0;
            }
            goto LABEL_119;
          }
          v32 = v72 == 100;
        }
        else
        {
          if ( a3 == 1402 )
            goto LABEL_82;
          v64 = a3 - 1201;
          if ( !v64 )
            goto LABEL_24;
          v65 = v64 - 1;
          if ( !v65 )
            goto LABEL_24;
          v66 = v65 - 1;
          if ( !v66 )
            goto LABEL_24;
          v67 = v66 - 98;
          if ( !v67 )
            goto LABEL_24;
          v68 = v67 - 1;
          if ( !v68 )
            goto LABEL_24;
          v32 = v68 == 99;
        }
LABEL_117:
        if ( !v32 )
          return 3222142977LL;
        goto LABEL_24;
      }
      if ( a3 == 1101 )
        goto LABEL_24;
      if ( a3 > 0x2C2 )
      {
        v61 = a3 - 801;
        if ( !v61 )
          goto LABEL_82;
        v62 = v61 - 1;
        if ( !v62 )
          goto LABEL_82;
        v60 = v62 - 1;
        if ( !v60 )
          goto LABEL_88;
      }
      else
      {
        if ( a3 == 706 )
          goto LABEL_82;
        v58 = a3 - 617;
        if ( !v58 )
          goto LABEL_67;
        v59 = v58 - 84;
        if ( !v59 )
          goto LABEL_24;
        v60 = v59 - 1;
        if ( !v60 )
          goto LABEL_24;
      }
      v63 = v60 - 1;
      if ( !v63 )
        goto LABEL_82;
      v45 = v63 - 1;
      if ( !v45 )
        goto LABEL_24;
    }
    else
    {
      if ( a3 == 616 )
        goto LABEL_88;
      if ( a3 > 0x25A )
      {
        if ( a3 > 0x261 )
        {
          v55 = a3 - 610;
          if ( !v55 )
            goto LABEL_24;
          v56 = v55 - 1;
          if ( v56 )
          {
            v57 = v56 - 1;
            if ( v57 )
            {
              v21 = v57 - 1;
              if ( v21 )
              {
LABEL_87:
                if ( v21 - 1 > 1 )
                  return 3222142977LL;
              }
            }
          }
LABEL_88:
          a4->vt = 19;
          goto LABEL_15;
        }
        if ( a3 == 609 )
          goto LABEL_82;
        v51 = a3 - 603;
        if ( !v51 )
          goto LABEL_74;
        v52 = v51 - 1;
        if ( !v52 )
          goto LABEL_74;
        v53 = v52 - 1;
        if ( v53 )
        {
          v54 = v53 - 1;
          if ( v54 )
          {
            v31 = v54 - 1;
            if ( !v31 )
              goto LABEL_82;
            goto LABEL_43;
          }
        }
LABEL_67:
        a4->vt = 18;
        LowPart = 2;
        goto LABEL_53;
      }
      if ( a3 == 602 )
        goto LABEL_52;
      if ( a3 > 0x134 )
      {
        v46 = a3 - 501;
        if ( !v46 )
          goto LABEL_52;
        v47 = v46 - 1;
        if ( !v47 )
          goto LABEL_74;
        v48 = v47 - 1;
        if ( !v48 )
          goto LABEL_82;
        v49 = v48 - 1;
        if ( !v49 )
          goto LABEL_82;
        v50 = v49 - 1;
        if ( v50 )
        {
          if ( v50 != 96 )
            return 3222142977LL;
LABEL_74:
          a4->vt = 31;
          BufferReader::ReadNullTerminated(a2, &a4->bstrVal);
          return 0;
        }
        goto LABEL_24;
      }
      if ( a3 == 308 )
        goto LABEL_24;
      v41 = a3 - 302;
      if ( !v41 )
        goto LABEL_82;
      v42 = v41 - 1;
      if ( !v42 )
        goto LABEL_36;
      v43 = v42 - 1;
      if ( !v43 )
        goto LABEL_74;
      v44 = v43 - 1;
      if ( !v44 )
        goto LABEL_67;
      v45 = v44 - 1;
      if ( !v45 )
        goto LABEL_67;
    }
    if ( v45 != 1 )
      return 3222142977LL;
    goto LABEL_82;
  }
  if ( a3 == 201 )
    goto LABEL_82;
  if ( a3 > 0x6E )
  {
    v15 = a3 - 111;
    if ( !v15 )
      goto LABEL_52;
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_52;
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_52;
      v19 = v18 - 1;
      if ( !v19 )
        goto LABEL_82;
      v20 = v19 - 1;
      if ( !v20 )
        goto LABEL_82;
      v21 = v20 - 1;
      if ( !v21 )
        goto LABEL_24;
      goto LABEL_87;
    }
    goto LABEL_88;
  }
  if ( a3 == 110 )
  {
LABEL_14:
    a4->vt = 3;
LABEL_15:
    LowPart = 4;
LABEL_53:
    v28 = &a4->hVal;
    goto LABEL_54;
  }
  v6 = a3 - 101;
  if ( !v6 )
    goto LABEL_82;
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_82;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_74;
  v9 = v8 - 1;
  if ( !v9 )
    goto LABEL_52;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_88;
  v11 = v10 - 1;
  if ( !v11 )
  {
    LowPart = 2;
    a4->vt = 2;
    goto LABEL_53;
  }
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_88;
  v13 = v12 - 1;
  if ( !v13 )
    goto LABEL_74;
  if ( v13 == 1 )
    goto LABEL_14;
  return 3222142977LL;
}

```

## disassembly

```asm
0x180014c50  push    rbx
0x180014c52  push    rsi
0x180014c53  push    rdi
0x180014c54  push    r14
0x180014c56  sub     rsp, 28h
0x180014c5a  xor     eax, eax
0x180014c5c  xorps   xmm0, xmm0
0x180014c5f  movups  xmmword ptr [r9], xmm0
0x180014c63  mov     [r9+10h], rax
0x180014c67  mov     rbx, r9
0x180014c6a  mov     eax, 0C9h
0x180014c6f  mov     rdi, rdx
0x180014c72  cmp     r8d, eax
0x180014c75  ja      loc_180014D78
0x180014c7b  jz      loc_180014FC7
0x180014c81  cmp     r8d, 6Eh ; 'n'
0x180014c85  ja      short loc_180014CFF
0x180014c87  jz      short loc_180014CDF
0x180014c89  sub     r8d, 65h ; 'e'
0x180014c8d  jz      loc_180014FC7
0x180014c93  sub     r8d, 1
0x180014c97  jz      loc_180014FC7
0x180014c9d  sub     r8d, 1
0x180014ca1  jz      loc_180014F7B
0x180014ca7  sub     r8d, 1
0x180014cab  jz      loc_180014EB2
0x180014cb1  sub     r8d, 1
0x180014cb5  jz      loc_180015014
0x180014cbb  sub     r8d, 1
0x180014cbf  jz      short loc_180014CF0
0x180014cc1  sub     r8d, 1
0x180014cc5  jz      loc_180015014
0x180014ccb  sub     r8d, 1
0x180014ccf  jz      loc_180014F7B
0x180014cd5  cmp     r8d, 1
0x180014cd9  jnz     loc_18001511E
0x180014cdf  mov     word ptr [r9], 3
0x180014ce5  mov     r8d, 4
0x180014ceb  jmp     loc_180014EBE
0x180014cf0  mov     r8d, 2
0x180014cf6  mov     [r9], r8w
0x180014cfa  jmp     loc_180014EBE
0x180014cff  sub     r8d, 6Fh ; 'o'
0x180014d03  jz      loc_180014EB2
0x180014d09  sub     r8d, 1
0x180014d0d  jz      loc_180015014
0x180014d13  sub     r8d, 1
0x180014d17  jz      loc_180014EB2
0x180014d1d  sub     r8d, 1
0x180014d21  jz      loc_180014EB2
0x180014d27  sub     r8d, 1
0x180014d2b  jz      loc_180014FC7
0x180014d31  sub     r8d, 1
0x180014d35  jz      loc_180014FC7
0x180014d3b  sub     r8d, 1
0x180014d3f  jnz     loc_180015004
0x180014d45  lea     rsi, [r9+8]
0x180014d49  mov     word ptr [r9], 41h ; 'A'
0x180014d4f  mov     rdx, rsi; void *
0x180014d52  mov     r8d, 4; unsigned __int64
0x180014d58  mov     rcx, rdi; this
0x180014d5b  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014d60  cmp     dword ptr [rsi], 0
0x180014d63  jz      loc_180015128
0x180014d69  mov     ecx, [rsi]; unsigned __int64
0x180014d6b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014d70  mov     r8d, [rsi]
0x180014d73  jmp     loc_180014E2B
0x180014d78  mov     eax, 12Dh
0x180014d7d  cmp     r8d, eax
0x180014d80  ja      loc_180014ED6
0x180014d86  jz      loc_180014F7B
0x180014d8c  mov     eax, 0D6h
0x180014d91  cmp     r8d, eax
0x180014d94  ja      loc_180014E61
0x180014d9a  jz      loc_180015014
0x180014da0  mov     eax, 0D1h
0x180014da5  cmp     r8d, eax
0x180014da8  ja      loc_180014E37
0x180014dae  jz      short loc_180014DE1
0x180014db0  sub     r8d, 0CAh
0x180014db7  jz      loc_180014FC7
0x180014dbd  sub     r8d, 1
0x180014dc1  jz      loc_180014F7B
0x180014dc7  sub     r8d, 3
0x180014dcb  jz      loc_180014D45
0x180014dd1  sub     r8d, 1
0x180014dd5  jz      short loc_180014DE1
0x180014dd7  cmp     r8d, 1
0x180014ddb  jnz     loc_18001511E
0x180014de1  lea     r14, [r9+8]
0x180014de5  mov     word ptr [r9], 1048h
0x180014deb  mov     rdx, r14; void *
0x180014dee  mov     r8d, 4; unsigned __int64
0x180014df4  mov     rcx, rdi; this
0x180014df7  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014dfc  cmp     dword ptr [r14], 0
0x180014e00  jz      loc_180015128
0x180014e06  mov     ecx, [r14]
0x180014e09  mov     eax, 10h
0x180014e0e  mul     rcx
0x180014e11  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014e18  cmovb   rax, rcx
0x180014e1c  mov     rcx, rax; unsigned __int64
0x180014e1f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014e24  mov     r8d, [r14]
0x180014e27  shl     r8, 4
0x180014e2b  mov     [rbx+10h], rax
0x180014e2f  mov     rdx, rax
0x180014e32  jmp     loc_180014EC2
0x180014e37  sub     r8d, 0D2h
0x180014e3e  jz      loc_180015014
0x180014e44  sub     r8d, 1
0x180014e48  jz      loc_180014FC7
0x180014e4e  sub     r8d, 1
0x180014e52  jz      loc_180015014
0x180014e58  cmp     r8d, 1
0x180014e5c  jmp     loc_180015118
0x180014e61  sub     r8d, 0D7h
0x180014e68  jz      loc_180015014
0x180014e6e  sub     r8d, 1
0x180014e72  jz      loc_180014F7B
0x180014e78  sub     r8d, 1
0x180014e7c  jz      loc_180014CDF
0x180014e82  sub     r8d, 1
0x180014e86  jz      loc_180014CDF
0x180014e8c  sub     r8d, 1
0x180014e90  jz      short loc_180014EB2
0x180014e92  sub     r8d, 1
0x180014e96  jz      loc_180015014
0x180014e9c  sub     r8d, 7
0x180014ea0  jz      short loc_180014EB2
0x180014ea2  sub     r8d, 1
0x180014ea6  jz      short loc_180014EB2
0x180014ea8  cmp     r8d, 1
0x180014eac  jnz     loc_18001511E
0x180014eb2  mov     word ptr [r9], 11h
0x180014eb8  mov     r8d, 1; unsigned __int64
0x180014ebe  lea     rdx, [r9+8]; void *
0x180014ec2  mov     rcx, rdi; this
0x180014ec5  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014eca  xor     eax, eax
0x180014ecc  add     rsp, 28h
0x180014ed0  pop     r14
0x180014ed2  pop     rdi
0x180014ed3  pop     rsi
0x180014ed4  pop     rbx
0x180014ed5  retn
0x180014ed6  mov     eax, 268h
0x180014edb  cmp     r8d, eax
0x180014ede  ja      loc_18001501F
0x180014ee4  jz      loc_180015014
0x180014eea  mov     eax, 25Ah
0x180014eef  cmp     r8d, eax
0x180014ef2  ja      loc_180014F92
0x180014ef8  jz      short loc_180014EB2
0x180014efa  mov     eax, 134h
0x180014eff  cmp     r8d, eax
0x180014f02  ja      short loc_180014F48
0x180014f04  jz      loc_180014D45
0x180014f0a  sub     r8d, 12Eh
0x180014f11  jz      loc_180014FC7
0x180014f17  sub     r8d, 1
0x180014f1b  jz      loc_180014DE1
0x180014f21  sub     r8d, 1
0x180014f25  jz      short loc_180014F7B
0x180014f27  sub     r8d, 1
0x180014f2b  jz      short loc_180014F37
0x180014f2d  sub     r8d, 1
0x180014f31  jnz     loc_18001508F
0x180014f37  mov     word ptr [r9], 12h
0x180014f3d  mov     r8d, 2
0x180014f43  jmp     loc_180014EBE
0x180014f48  sub     r8d, 1F5h
0x180014f4f  jz      loc_180014EB2
0x180014f55  sub     r8d, 1
0x180014f59  jz      short loc_180014F7B
0x180014f5b  sub     r8d, 1
0x180014f5f  jz      short loc_180014FC7
0x180014f61  sub     r8d, 1
0x180014f65  jz      short loc_180014FC7
0x180014f67  sub     r8d, 1
0x180014f6b  jz      loc_180014D45
0x180014f71  cmp     r8d, 60h ; '`'
0x180014f75  jnz     loc_18001511E
0x180014f7b  lea     rdx, [r9+8]; wchar_t **
0x180014f7f  mov     word ptr [r9], 1Fh
0x180014f85  mov     rcx, rdi; this
0x180014f88  call    ?ReadNullTerminated@BufferReader@@QEAAXPEAPEA_W@Z; BufferReader::ReadNullTerminated(wchar_t * *)
0x180014f8d  jmp     loc_180014ECA
0x180014f92  mov     eax, 261h
0x180014f97  cmp     r8d, eax
0x180014f9a  ja      short loc_180014FE5
0x180014f9c  jz      short loc_180014FC7
0x180014f9e  sub     r8d, 25Bh
0x180014fa5  jz      short loc_180014F7B
0x180014fa7  sub     r8d, 1
0x180014fab  jz      short loc_180014F7B
0x180014fad  sub     r8d, 1
0x180014fb1  jz      short loc_180014F37
0x180014fb3  sub     r8d, 1
0x180014fb7  jz      loc_180014F37
0x180014fbd  sub     r8d, 1
0x180014fc1  jnz     loc_180014E58
0x180014fc7  mov     esi, 10h
0x180014fcc  mov     word ptr [r9], 48h ; 'H'
0x180014fd2  mov     ecx, esi; unsigned __int64
0x180014fd4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014fd9  mov     [rbx+8], rax
0x180014fdd  mov     r8d, esi
0x180014fe0  jmp     loc_180014E2F
0x180014fe5  sub     r8d, 262h
0x180014fec  jz      loc_180014D45
0x180014ff2  sub     r8d, 1
0x180014ff6  jz      short loc_180015014
0x180014ff8  sub     r8d, 1
0x180014ffc  jz      short loc_180015014
0x180014ffe  sub     r8d, 1
0x180015002  jz      short loc_180015014
0x180015004  sub     r8d, 1
0x180015008  jz      short loc_180015014
0x18001500a  cmp     r8d, 1
0x18001500e  jnz     loc_18001511E
0x180015014  mov     word ptr [r9], 13h
0x18001501a  jmp     loc_180014CE5
0x18001501f  mov     eax, 44Dh
0x180015024  cmp     r8d, eax
0x180015027  ja      short loc_18001509E
0x180015029  jz      loc_180014D45
0x18001502f  mov     eax, 2C2h
0x180015034  cmp     r8d, eax
0x180015037  ja      short loc_18001505E
0x180015039  jz      short loc_180014FC7
0x18001503b  sub     r8d, 269h
0x180015042  jz      loc_180014F37
0x180015048  sub     r8d, 54h ; 'T'
0x18001504c  jz      loc_180014D45
0x180015052  sub     r8d, 1
0x180015056  jz      loc_180014D45
0x18001505c  jmp     short loc_18001507B
0x18001505e  sub     r8d, 321h
0x180015065  jz      loc_180014FC7
0x18001506b  sub     r8d, 1
0x18001506f  jz      loc_180014FC7
0x180015075  sub     r8d, 1
0x180015079  jz      short loc_180015014
0x18001507b  sub     r8d, 1
0x18001507f  jz      loc_180014FC7
0x180015085  sub     r8d, 1
0x180015089  jz      loc_180014D45
0x18001508f  cmp     r8d, 1
0x180015093  jz      loc_180014FC7
0x180015099  jmp     loc_18001511E
0x18001509e  mov     eax, 57Ah
0x1800150a3  cmp     r8d, eax
0x1800150a6  ja      short loc_1800150E9
0x1800150a8  jz      loc_180014FC7
0x1800150ae  sub     r8d, 4B1h
0x1800150b5  jz      loc_180014D45
0x1800150bb  sub     r8d, 1
0x1800150bf  jz      loc_180014D45
0x1800150c5  sub     r8d, 1
0x1800150c9  jz      loc_180014D45
0x1800150cf  sub     r8d, 62h ; 'b'
0x1800150d3  jz      loc_180014D45
0x1800150d9  sub     r8d, 1
0x1800150dd  jz      loc_180014D45
0x1800150e3  cmp     r8d, 63h ; 'c'
0x1800150e7  jmp     short loc_180015118
0x1800150e9  sub     r8d, 57Bh
0x1800150f0  jz      loc_180014EB2
0x1800150f6  sub     r8d, 1
0x1800150fa  jz      loc_180014EB2
0x180015100  sub     r8d, 1
0x180015104  jz      loc_180014FC7
0x18001510a  sub     r8d, 60h ; '`'
0x18001510e  jz      loc_180014D45
0x180015114  cmp     r8d, 64h ; 'd'
0x180015118  jz      loc_180014D45
0x18001511e  mov     eax, 0C00E0001h
0x180015123  jmp     loc_180014ECC
0x180015128  mov     qword ptr [rbx+10h], 0
0x180015130  jmp     loc_180014ECA
```
