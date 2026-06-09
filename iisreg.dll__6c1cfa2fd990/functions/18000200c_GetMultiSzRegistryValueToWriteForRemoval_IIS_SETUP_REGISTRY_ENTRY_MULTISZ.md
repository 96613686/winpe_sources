# GetMultiSzRegistryValueToWriteForRemoval(IIS_SETUP_REGISTRY_ENTRY *,MULTISZ *)

- ea: `0x18000200c`
- end: `0x180002244`
- name: `?GetMultiSzRegistryValueToWriteForRemoval@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVMULTISZ@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *, struct MULTISZ *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180002b90`

## callees

- `0x180001ab0`
- `0x18000200c`
- `0x18000260c`
- `0x18000283c`
- `0x180002ff8`
- `0x1800033ac`
- `0x1800034b8`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800021d6`
- `KERNEL32!GetLastError` at `0x1800021d6`

## pseudocode

```c
__int64 __fastcall GetMultiSzRegistryValueToWriteForRemoval(struct IIS_SETUP_REGISTRY_ENTRY *a1, struct MULTISZ *this)
{
  _QWORD *v3; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  HKEY v10; // rax
  __int64 i; // r8
  signed int SetupRegistryEntryAsMultiSz; // ebx
  const unsigned __int16 *v13; // rdi
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned __int16 *v16; // rdx
  size_t v17; // r8
  __int64 j; // r9
  signed int LastError; // eax
  _QWORD v21[4]; // [rsp+20h] [rbp-79h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-59h]
  int v23; // [rsp+48h] [rbp-51h]
  __int16 v24; // [rsp+4Ch] [rbp-4Dh]
  __int64 v25; // [rsp+50h] [rbp-49h]
  _QWORD v26[4]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *Src; // [rsp+78h] [rbp-21h]
  int v28; // [rsp+80h] [rbp-19h]
  __int16 v29; // [rsp+84h] [rbp-15h]
  __int64 v30; // [rsp+88h] [rbp-11h]
  _QWORD v31[4]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD *v32; // [rsp+B0h] [rbp+17h]
  int v33; // [rsp+B8h] [rbp+1Fh]
  __int16 v34; // [rsp+BCh] [rbp+23h]
  __int64 v35; // [rsp+C0h] [rbp+27h]

  v24 = 256;
  v21[0] = 0;
  v3 = v21;
  v22 = (unsigned __int64)v21;
  v5 = 0;
  v23 = 32;
  while ( 1 )
  {
    *((_WORD *)v3 + v5++) = 0;
    if ( v5 == 2 )
      break;
    v3 = (_QWORD *)v22;
  }
  v6 = v31;
  v25 = 2;
  v32 = v31;
  v7 = 0;
  v31[0] = 0;
  v33 = 32;
  v34 = 256;
  while ( 1 )
  {
    *((_WORD *)v6 + v7++) = 0;
    if ( v7 == 2 )
      break;
    v6 = v32;
  }
  v8 = (unsigned __int16 *)v26;
  v35 = 2;
  Src = (unsigned __int16 *)v26;
  v9 = 0;
  v26[0] = 0;
  v28 = 32;
  v29 = 256;
  while ( 1 )
  {
    v8[v9++] = 0;
    if ( v9 == 2 )
      break;
    v8 = Src;
  }
  v30 = 2;
  if ( a1 && this )
  {
    v10 = ConvertStringToHKey(*((wchar_t **)a1 + 1));
    if ( (int)ReadMultiSzRegistryValue(v10, *((LPCWSTR *)a1 + 2), *((LPCWSTR *)a1 + 3), (struct MULTISZ *)v21) < 0 )
    {
      for ( i = 0; i != 2; ++i )
        *(_WORD *)(v22 + 2 * i) = 0;
      v25 = 2;
    }
    SetupRegistryEntryAsMultiSz = ReadSetupRegistryEntryAsMultiSz(a1, (struct MULTISZ *)v31);
    if ( SetupRegistryEntryAsMultiSz >= 0 )
    {
      v13 = (const unsigned __int16 *)(v22 & -(__int64)(*(_WORD *)v22 != 0));
      if ( v13 )
      {
        do
        {
          if ( !MULTISZ::FindStringNoCase((MULTISZ *)v31, v13) && v13 )
          {
            v14 = -1;
            do
              ++v14;
            while ( v13[v14] );
            MULTISZ::AuxAppend((MULTISZ *)v26, v13, (unsigned int)(2 * v14), 1);
          }
          v15 = -1;
          do
            ++v15;
          while ( v13[v15] );
          v13 += v15 + 1;
        }
        while ( *v13 );
      }
      v16 = Src;
      v17 = (unsigned int)(2 * v30);
      if ( *((_QWORD *)this + 4) )
      {
        for ( j = 0; j != 2; ++j )
          *(_WORD *)(*((_QWORD *)this + 4) + 2 * j) = 0;
        *((_QWORD *)this + 6) = 2;
      }
      if ( v16 )
      {
        if ( !(unsigned int)MULTISZ::AuxAppend(this, v16, v17, 0) )
        {
          LastError = GetLastError();
          SetupRegistryEntryAsMultiSz = LastError;
          if ( LastError > 0 )
            SetupRegistryEntryAsMultiSz = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  else
  {
    SetupRegistryEntryAsMultiSz = -2147024809;
  }
  if ( (_BYTE)v29 )
    BUFFER::FreeMemoryInternal((BUFFER *)v26);
  if ( (_BYTE)v34 )
    BUFFER::FreeMemoryInternal((BUFFER *)v31);
  if ( (_BYTE)v24 )
    BUFFER::FreeMemoryInternal((BUFFER *)v21);
  return (unsigned int)SetupRegistryEntryAsMultiSz;
}

```

## disassembly

```asm
0x18000200c  mov     [rsp-8+arg_10], rbx
0x180002011  push    rbp
0x180002012  push    rsi
0x180002013  push    rdi
0x180002014  push    r14
0x180002016  push    r15
0x180002018  lea     rbp, [rsp-37h]
0x18000201d  sub     rsp, 0D0h
0x180002024  mov     rax, cs:__security_cookie
0x18000202b  xor     rax, rsp
0x18000202e  mov     [rbp+57h+var_28], rax
0x180002032  xor     r14d, r14d
0x180002035  mov     [rbp+57h+var_A4], 100h
0x18000203b  mov     rsi, rdx
0x18000203e  mov     [rbp+57h+var_D0], r14
0x180002042  lea     rdx, [rbp+57h+var_D0]
0x180002046  mov     rbx, rcx
0x180002049  mov     [rbp+57h+var_B0], rdx
0x18000204d  mov     ecx, r14d
0x180002050  lea     r8d, [r14+20h]
0x180002054  mov     [rbp+57h+var_A8], r8d
0x180002058  lea     r15d, [r14+2]
0x18000205c  mov     [rdx+rcx*2], r14w
0x180002061  inc     rcx
0x180002064  cmp     rcx, r15
0x180002067  jz      short loc_18000206F
0x180002069  mov     rdx, [rbp+57h+var_B0]
0x18000206d  jmp     short loc_18000205C
0x18000206f  lea     rdx, [rbp+57h+var_60]
0x180002073  mov     [rbp+57h+var_A0], r15
0x180002077  mov     [rbp+57h+var_40], rdx
0x18000207b  mov     rcx, r14
0x18000207e  mov     [rbp+57h+var_60], r14
0x180002082  mov     [rbp+57h+var_38], r8d
0x180002086  mov     [rbp+57h+var_34], 100h
0x18000208c  mov     [rdx+rcx*2], r14w
0x180002091  inc     rcx
0x180002094  cmp     rcx, r15
0x180002097  jz      short loc_18000209F
0x180002099  mov     rdx, [rbp+57h+var_40]
0x18000209d  jmp     short loc_18000208C
0x18000209f  lea     rdx, [rbp+57h+var_98]
0x1800020a3  mov     [rbp+57h+var_30], r15
0x1800020a7  mov     [rbp+57h+Src], rdx
0x1800020ab  mov     rcx, r14
0x1800020ae  mov     [rbp+57h+var_98], r14
0x1800020b2  mov     [rbp+57h+var_70], r8d
0x1800020b6  mov     [rbp+57h+var_6C], 100h
0x1800020bc  mov     [rdx+rcx*2], r14w
0x1800020c1  inc     rcx
0x1800020c4  cmp     rcx, r15
0x1800020c7  jz      short loc_1800020CF
0x1800020c9  mov     rdx, [rbp+57h+Src]
0x1800020cd  jmp     short loc_1800020BC
0x1800020cf  mov     [rbp+57h+var_68], r15
0x1800020d3  test    rbx, rbx
0x1800020d6  jz      loc_1800021ED
0x1800020dc  test    rsi, rsi
0x1800020df  jz      loc_1800021ED
0x1800020e5  mov     rcx, [rbx+8]; String1
0x1800020e9  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x1800020ee  mov     r8, [rbx+18h]; lpValueName
0x1800020f2  lea     r9, [rbp+57h+var_D0]; this
0x1800020f6  mov     rdx, [rbx+10h]; lpSubKey
0x1800020fa  mov     rcx, rax; hKey
0x1800020fd  call    ?ReadMultiSzRegistryValue@@YAJPEAUHKEY__@@PEAG1PEAVMULTISZ@@@Z; ReadMultiSzRegistryValue(HKEY__ *,ushort *,ushort *,MULTISZ *)
0x180002102  test    eax, eax
0x180002104  jns     short loc_18000211E
0x180002106  mov     r8, r14
0x180002109  mov     rax, [rbp+57h+var_B0]
0x18000210d  mov     [rax+r8*2], r14w
0x180002112  inc     r8
0x180002115  cmp     r8, r15
0x180002118  jnz     short loc_180002109
0x18000211a  mov     [rbp+57h+var_A0], r15
0x18000211e  lea     rdx, [rbp+57h+var_60]; struct MULTISZ *
0x180002122  mov     rcx, rbx; struct IIS_SETUP_REGISTRY_ENTRY *
0x180002125  call    ?ReadSetupRegistryEntryAsMultiSz@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVMULTISZ@@@Z; ReadSetupRegistryEntryAsMultiSz(IIS_SETUP_REGISTRY_ENTRY *,MULTISZ *)
0x18000212a  mov     ebx, eax
0x18000212c  test    eax, eax
0x18000212e  js      loc_1800021F2
0x180002134  mov     rdx, [rbp+57h+var_B0]
0x180002138  movzx   ecx, word ptr [rdx]
0x18000213b  neg     cx
0x18000213e  sbb     rdi, rdi
0x180002141  and     rdi, rdx
0x180002144  jz      short loc_180002199
0x180002146  mov     rdx, rdi; unsigned __int16 *
0x180002149  lea     rcx, [rbp+57h+var_60]; this
0x18000214d  call    ?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x180002152  test    eax, eax
0x180002154  jnz     short loc_18000217E
0x180002156  test    rdi, rdi
0x180002159  jz      short loc_18000217E
0x18000215b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000215f  inc     r8
0x180002162  cmp     [rdi+r8*2], r14w
0x180002167  jnz     short loc_18000215F
0x180002169  add     r8d, r8d; Size
0x18000216c  lea     rcx, [rbp+57h+var_98]; this
0x180002170  mov     r9d, 1; int
0x180002176  mov     rdx, rdi; Src
0x180002179  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x18000217e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002182  inc     rax
0x180002185  cmp     [rdi+rax*2], r14w
0x18000218a  jnz     short loc_180002182
0x18000218c  lea     rdi, [rdi+rax*2]
0x180002190  add     rdi, r15
0x180002193  cmp     [rdi], r14w
0x180002197  jnz     short loc_180002146
0x180002199  mov     eax, dword ptr [rbp+57h+var_68]
0x18000219c  mov     rdx, [rbp+57h+Src]; Src
0x1800021a0  lea     r8d, [rax+rax]; Size
0x1800021a4  cmp     [rsi+20h], r14
0x1800021a8  jz      short loc_1800021C2
0x1800021aa  mov     r9, r14
0x1800021ad  mov     rcx, [rsi+20h]
0x1800021b1  mov     [rcx+r9*2], r14w
0x1800021b6  inc     r9
0x1800021b9  cmp     r9, r15
0x1800021bc  jnz     short loc_1800021AD
0x1800021be  mov     [rsi+30h], r15
0x1800021c2  test    rdx, rdx
0x1800021c5  jz      short loc_1800021F2
0x1800021c7  xor     r9d, r9d; int
0x1800021ca  mov     rcx, rsi; this
0x1800021cd  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x1800021d2  test    eax, eax
0x1800021d4  jnz     short loc_1800021F2
0x1800021d6  call    cs:__imp_GetLastError
0x1800021dc  mov     ebx, eax
0x1800021de  test    eax, eax
0x1800021e0  jle     short loc_1800021F2
0x1800021e2  movzx   ebx, ax
0x1800021e5  or      ebx, 80070000h
0x1800021eb  jmp     short loc_1800021F2
0x1800021ed  mov     ebx, 80070057h
0x1800021f2  cmp     byte ptr [rbp+57h+var_6C], r14b
0x1800021f6  jz      short loc_180002201
0x1800021f8  lea     rcx, [rbp+57h+var_98]; this
0x1800021fc  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002201  cmp     byte ptr [rbp+57h+var_34], r14b
0x180002205  jz      short loc_180002210
0x180002207  lea     rcx, [rbp+57h+var_60]; this
0x18000220b  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002210  cmp     byte ptr [rbp+57h+var_A4], r14b
0x180002214  jz      short loc_18000221F
0x180002216  lea     rcx, [rbp+57h+var_D0]; this
0x18000221a  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x18000221f  mov     eax, ebx
0x180002221  mov     rcx, [rbp+57h+var_28]
0x180002225  xor     rcx, rsp; StackCookie
0x180002228  call    __security_check_cookie
0x18000222d  mov     rbx, [rsp+0F0h+arg_10]
0x180002235  add     rsp, 0D0h
0x18000223c  pop     r15
0x18000223e  pop     r14
0x180002240  pop     rdi
0x180002241  pop     rsi
0x180002242  pop     rbp
0x180002243  retn
```
