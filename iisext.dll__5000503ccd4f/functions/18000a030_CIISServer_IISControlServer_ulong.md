# CIISServer::IISControlServer(ulong)

- ea: `0x18000a030`
- end: `0x18000a2d4`
- name: `?IISControlServer@CIISServer@@QEAAJK@Z`
- size: `676`
- prototype: `__int64 __fastcall(CIISServer *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180009de0`
- `0x18000a4f0`
- `0x18000a520`
- `0x18000a530`

## callees

- `0x180003de8`
- `0x18000a030`
- `0x18000a2dc`
- `0x180012010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000a26d`
- `KERNEL32!Sleep` at `0x18000a26d`

## pseudocode

```c
__int64 __fastcall CIISServer::IISControlServer(unsigned __int16 **this, unsigned int a2)
{
  unsigned int v2; // edi
  int v5; // ebx
  int v6; // r12d
  int v7; // r14d
  __int64 result; // rax
  _QWORD *v9; // r13
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int v13; // r15d
  __int64 v14; // rcx
  unsigned __int16 *v15; // r8
  signed int v16; // eax
  unsigned __int16 *v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  int v19; // [rsp+38h] [rbp-28h]
  int v20; // [rsp+3Ch] [rbp-24h]
  __int64 v21; // [rsp+40h] [rbp-20h]
  unsigned int *v22; // [rsp+48h] [rbp-18h]
  __int64 v23; // [rsp+50h] [rbp-10h]
  unsigned int v24; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+50h] BYREF
  int v26; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  v25 = 0;
  v24 = 0;
  switch ( a2 )
  {
    case 1u:
      v6 = 1;
      break;
    case 2u:
      v7 = 4;
      v6 = 3;
      goto LABEL_11;
    case 3u:
      v7 = 4;
      v6 = 5;
      goto LABEL_11;
    case 4u:
      v6 = 7;
      break;
    default:
      v5 = -2147024809;
      goto LABEL_33;
  }
  v7 = 2;
LABEL_11:
  result = CIISServer::IISGetServerState((CIISServer *)this, 4u, &v24);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( v24 == v7 )
      return result;
    v9 = this + 15;
    v5 = OpenAdminBaseKey(this[8], this[9], 2u, (struct IMSAdminBaseW **)this + 15, &v25);
    if ( v5 < 0 )
    {
      v2 = v25;
    }
    else
    {
      v10 = *v9;
      v26 = 0;
      v19 = 1;
      v20 = 1;
      v22 = (unsigned int *)&v26;
      v23 = 0;
      v2 = v25;
      v18 = 0x100000044BLL;
      v21 = 4;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int64 *))(*(_QWORD *)v10 + 72LL))(
             v10,
             v25,
             &hMem,
             &v18);
      if ( v5 >= 0 )
      {
        v11 = *v9;
        v19 = 1;
        v20 = 1;
        v22 = &v25;
        v25 = a2;
        v21 = 4;
        v23 = 0;
        v18 = 0x10000003F4LL;
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int64 *))(*(_QWORD *)v11 + 72LL))(
               v11,
               v2,
               &hMem,
               &v18);
        if ( v5 >= 0 )
        {
          v13 = 0;
          if ( *v9 )
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 144LL))(*v9, v2);
          while ( 1 )
          {
            v5 = CIISServer::IISGetServerState((CIISServer *)this, v12, &v24);
            if ( v5 < 0 )
              break;
            v14 = *v9;
            v15 = this[9];
            v25 = 0;
            v19 = 1;
            v20 = 1;
            v22 = &v25;
            v26 = 0;
            v18 = 1099;
            v21 = 4;
            v23 = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, __int64 *, int *))(*(_QWORD *)v14 + 80LL))(
                   v14,
                   0,
                   v15,
                   &v18,
                   &v26);
            if ( v5 == -2146646015 )
              v5 = 1;
            v16 = v25;
            if ( (int)v25 > 0 )
              v16 = (unsigned __int16)v25 | 0x80070000;
            if ( v5 < 0 || v24 != v6 && v24 == v7 )
              break;
            if ( v16 < 0 )
            {
              v5 = v16;
              break;
            }
            Sleep(0x1F4u);
            v13 += 500;
            if ( v13 >= 0xEA60 )
            {
              v5 = -2147023843;
              break;
            }
          }
        }
      }
    }
  }
LABEL_33:
  v17 = this[15];
  if ( v17 )
  {
    if ( v2 )
      (*(void (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v17 + 144LL))(v17, v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a030  mov     [rsp-38h+arg_0], rbx
0x18000a035  push    rbp
0x18000a036  push    rsi
0x18000a037  push    rdi
0x18000a038  push    r12
0x18000a03a  push    r13
0x18000a03c  push    r14
0x18000a03e  push    r15
0x18000a040  mov     rbp, rsp
0x18000a043  sub     rsp, 60h
0x18000a047  xor     edi, edi
0x18000a049  mov     eax, edx
0x18000a04b  mov     [rbp+arg_10], edi
0x18000a04e  mov     r15d, edx
0x18000a051  mov     [rbp+arg_8], edi
0x18000a054  mov     rsi, rcx
0x18000a057  lea     ecx, [rdi+2]
0x18000a05a  lea     edx, [rdi+4]; unsigned int
0x18000a05d  sub     eax, 1
0x18000a060  jz      short loc_18000A099
0x18000a062  sub     eax, 1
0x18000a065  jz      short loc_18000A08E
0x18000a067  sub     eax, 1
0x18000a06a  jz      short loc_18000A083
0x18000a06c  cmp     eax, 1
0x18000a06f  jz      short loc_18000A07B
0x18000a071  mov     ebx, 80070057h
0x18000a076  jmp     loc_18000A29C
0x18000a07b  mov     r12d, 7
0x18000a081  jmp     short loc_18000A09F
0x18000a083  mov     r14d, edx
0x18000a086  mov     r12d, 5
0x18000a08c  jmp     short loc_18000A0A2
0x18000a08e  mov     r14d, edx
0x18000a091  mov     r12d, 3
0x18000a097  jmp     short loc_18000A0A2
0x18000a099  mov     r12d, 1
0x18000a09f  mov     r14d, ecx
0x18000a0a2  lea     r8, [rbp+arg_8]; unsigned int *
0x18000a0a6  mov     rcx, rsi; this
0x18000a0a9  call    ?IISGetServerState@CIISServer@@QEAAJKPEAK@Z; CIISServer::IISGetServerState(ulong,ulong *)
0x18000a0ae  mov     ebx, eax
0x18000a0b0  test    eax, eax
0x18000a0b2  js      loc_18000A29C
0x18000a0b8  cmp     [rbp+arg_8], r14d
0x18000a0bc  jz      loc_18000A2BC
0x18000a0c2  mov     rdx, [rsi+48h]; unsigned __int16 *
0x18000a0c6  lea     rax, [rbp+arg_10]
0x18000a0ca  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18000a0ce  lea     r13, [rsi+78h]
0x18000a0d2  mov     r9, r13; struct IMSAdminBaseW **
0x18000a0d5  mov     [rsp+60h+var_40], rax; unsigned int *
0x18000a0da  mov     r8d, 2; unsigned int
0x18000a0e0  call    ?OpenAdminBaseKey@@YAJPEAG0KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x18000a0e5  mov     ebx, eax
0x18000a0e7  test    eax, eax
0x18000a0e9  js      loc_18000A299
0x18000a0ef  mov     rcx, [r13+0]
0x18000a0f3  lea     r9, [rbp+var_30]
0x18000a0f7  mov     eax, 1
0x18000a0fc  mov     [rbp+arg_18], edi
0x18000a0ff  mov     [rbp+var_28], eax
0x18000a102  lea     r8, hMem
0x18000a109  mov     [rbp+var_24], eax
0x18000a10c  lea     rax, [rbp+arg_18]
0x18000a110  mov     [rbp+var_18], rax
0x18000a114  mov     [rbp+var_10], rdi
0x18000a118  mov     edi, [rbp+arg_10]
0x18000a11b  mov     edx, edi
0x18000a11d  mov     dword ptr [rbp+var_30], 44Bh
0x18000a124  mov     dword ptr [rbp+var_30+4], 10h
0x18000a12b  mov     [rbp+var_20], 4
0x18000a133  mov     rax, [rcx]
0x18000a136  mov     rax, [rax+48h]
0x18000a13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a13f  mov     ebx, eax
0x18000a141  test    eax, eax
0x18000a143  js      loc_18000A29C
0x18000a149  mov     rcx, [r13+0]
0x18000a14d  mov     eax, 1
0x18000a152  mov     [rbp+var_28], eax
0x18000a155  mov     [rbp+var_24], eax
0x18000a158  lea     rax, [rbp+arg_10]
0x18000a15c  mov     [rbp+var_18], rax
0x18000a160  mov     [rbp+arg_10], r15d
0x18000a164  mov     [rbp+var_20], 4
0x18000a16c  mov     [rbp+var_10], 0
0x18000a174  mov     dword ptr [rbp+var_30], 3F4h
0x18000a17b  mov     dword ptr [rbp+var_30+4], 10h
0x18000a182  mov     rax, [rcx]
0x18000a185  lea     r9, [rbp+var_30]
0x18000a189  lea     r8, hMem
0x18000a190  mov     edx, edi
0x18000a192  mov     rax, [rax+48h]
0x18000a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a19b  mov     ebx, eax
0x18000a19d  test    eax, eax
0x18000a19f  js      loc_18000A29C
0x18000a1a5  mov     rcx, [r13+0]
0x18000a1a9  xor     r15d, r15d
0x18000a1ac  test    rcx, rcx
0x18000a1af  jz      short loc_18000A1C2
0x18000a1b1  mov     rax, [rcx]
0x18000a1b4  mov     edx, edi
0x18000a1b6  mov     rax, [rax+90h]
0x18000a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c2  lea     r8, [rbp+arg_8]; unsigned int *
0x18000a1c6  mov     rcx, rsi; this
0x18000a1c9  call    ?IISGetServerState@CIISServer@@QEAAJKPEAK@Z; CIISServer::IISGetServerState(ulong,ulong *)
0x18000a1ce  mov     ebx, eax
0x18000a1d0  test    eax, eax
0x18000a1d2  js      loc_18000A29C
0x18000a1d8  mov     rcx, [r13+0]
0x18000a1dc  lea     rdx, [rbp+arg_18]
0x18000a1e0  mov     r8, [rsi+48h]
0x18000a1e4  lea     r9, [rbp+var_30]
0x18000a1e8  mov     eax, 1
0x18000a1ed  mov     [rbp+arg_10], 0
0x18000a1f4  mov     [rbp+var_28], eax
0x18000a1f7  mov     [rbp+var_24], eax
0x18000a1fa  lea     rax, [rbp+arg_10]
0x18000a1fe  mov     [rbp+var_18], rax
0x18000a202  mov     [rbp+arg_18], 0
0x18000a209  mov     [rbp+var_30], 44Bh
0x18000a211  mov     [rbp+var_20], 4
0x18000a219  mov     [rbp+var_10], 0
0x18000a221  mov     rax, [rcx]
0x18000a224  mov     [rsp+60h+var_40], rdx
0x18000a229  xor     edx, edx
0x18000a22b  mov     rax, [rax+50h]
0x18000a22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a234  cmp     eax, 800CC801h
0x18000a239  mov     ebx, eax
0x18000a23b  mov     eax, 1
0x18000a240  cmovz   ebx, eax
0x18000a243  mov     eax, [rbp+arg_10]
0x18000a246  test    eax, eax
0x18000a248  jle     short loc_18000A252
0x18000a24a  movzx   eax, ax
0x18000a24d  or      eax, 80070000h
0x18000a252  test    ebx, ebx
0x18000a254  js      short loc_18000A29C
0x18000a256  cmp     [rbp+arg_8], r12d
0x18000a25a  jz      short loc_18000A262
0x18000a25c  cmp     [rbp+arg_8], r14d
0x18000a260  jz      short loc_18000A285
0x18000a262  test    eax, eax
0x18000a264  js      short loc_18000A295
0x18000a266  mov     ebx, 1F4h
0x18000a26b  mov     ecx, ebx; dwMilliseconds
0x18000a26d  call    cs:__imp_Sleep
0x18000a273  add     r15d, ebx
0x18000a276  cmp     r15d, 0EA60h
0x18000a27d  jb      loc_18000A1C2
0x18000a283  jmp     short loc_18000A28E
0x18000a285  cmp     r15d, 0EA60h
0x18000a28c  jb      short loc_18000A29C
0x18000a28e  mov     ebx, 8007041Dh
0x18000a293  jmp     short loc_18000A29C
0x18000a295  mov     ebx, eax
0x18000a297  jmp     short loc_18000A29C
0x18000a299  mov     edi, [rbp+arg_10]
0x18000a29c  mov     rcx, [rsi+78h]
0x18000a2a0  test    rcx, rcx
0x18000a2a3  jz      short loc_18000A2BA
0x18000a2a5  test    edi, edi
0x18000a2a7  jz      short loc_18000A2BA
0x18000a2a9  mov     rax, [rcx]
0x18000a2ac  mov     edx, edi
0x18000a2ae  mov     rax, [rax+90h]
0x18000a2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ba  mov     eax, ebx
0x18000a2bc  mov     rbx, [rsp+60h+arg_0]
0x18000a2c4  add     rsp, 60h
0x18000a2c8  pop     r15
0x18000a2ca  pop     r14
0x18000a2cc  pop     r13
0x18000a2ce  pop     r12
0x18000a2d0  pop     rdi
0x18000a2d1  pop     rsi
0x18000a2d2  pop     rbp
0x18000a2d3  retn
```
