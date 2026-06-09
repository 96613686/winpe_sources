# SafeArray_ValidateBuffer(ulong *,uchar *,tagSAFEARRAY const *,int)

- ea: `0x18001ea5c`
- end: `0x18001f2be`
- name: `?SafeArray_ValidateBuffer@@YAXPEAKPEAEPEBUtagSAFEARRAY@@H@Z`
- size: `2146`
- prototype: `void __fastcall(unsigned int *pFlags, unsigned __int8 *, const struct tagSAFEARRAY *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b890`
- `0x18001e030`

## callees

- `0x18000bc14`
- `0x18000bc34`
- `0x18000c190`
- `0x18001b354`
- `0x18001ea5c`
- `0x18001f2c4`
- `0x180049d54`
- `0x18004e530`
- `0x18007a3fc`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001f11f`
- `RPCRT4!RpcRaiseException` at `0x18001f1e5`
- `RPCRT4!RpcRaiseException` at `0x18001f11f`
- `RPCRT4!RpcRaiseException` at `0x18001f1e5`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001eab8`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001eee7`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001eab8`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001eee7`

## string_xrefs

- `0x18001ee8b`: `Unexpected end of buffer during BUFFER.Read()`
- `0x18001f12d`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f141`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f151`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f165`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f17c`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f1be`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001f1d2`: `Unexpected end of buffer during BUFFER.Increment(%lu)`

## pseudocode

```c
void __fastcall SafeArray_ValidateBuffer(
        unsigned int *pFlags,
        unsigned __int8 *a2,
        const struct tagSAFEARRAY *a3,
        int a4)
{
  unsigned int v7; // r15d
  RPC_STATUS UserMarshalInfo; // eax
  unsigned __int64 v9; // r8
  unsigned __int8 *v10; // rdi
  int v11; // ecx
  __int64 v12; // rdx
  unsigned __int8 *v13; // rdx
  unsigned __int64 v14; // rax
  char *v15; // rcx
  int v16; // r10d
  unsigned __int16 *v17; // rcx
  unsigned int v18; // r11d
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ebx
  unsigned int v21; // r13d
  _DWORD *v22; // rcx
  int v23; // r9d
  char *v24; // rdx
  unsigned int v25; // ecx
  char *v26; // r14
  __int64 v27; // r12
  char *v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // edx
  __int64 v31; // rcx
  char *v32; // rcx
  int v33; // eax
  unsigned int v34; // esi
  __int64 v35; // rbx
  unsigned int v36; // ecx
  char *v37; // r14
  __int64 v38; // rcx
  __int16 v39; // dx
  unsigned __int16 v40; // r8
  bool v41; // zf
  int v42; // ecx
  RPC_STATUS v43; // eax
  __int64 v44; // r8
  __int64 v45; // r9
  unsigned int RecordSize; // ebx
  bool v47; // zf
  bool v48; // zf
  unsigned int v49; // eax
  __int16 v50; // ax
  __int16 v51; // ax
  __int16 v52; // ax
  USHORT fFeatures; // dx
  __int16 v54; // [rsp+28h] [rbp-79h]
  _QWORD v55[3]; // [rsp+30h] [rbp-71h] BYREF
  unsigned int BufferSize; // [rsp+48h] [rbp-59h]
  unsigned int v57; // [rsp+50h] [rbp-51h]
  unsigned int v58[2]; // [rsp+58h] [rbp-49h]
  int v59; // [rsp+60h] [rbp-41h]
  NDR_USER_MARSHAL_INFO pMarshalInfo; // [rsp+68h] [rbp-39h] BYREF

  v7 = 0;
  if ( !(unsigned int)ShieldActivated() )
    return;
  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  UserMarshalInfo = NdrGetUserMarshalInfo(pFlags, 1u, &pMarshalInfo);
  if ( UserMarshalInfo )
    RpcRaiseException(UserMarshalInfo);
  v10 = (unsigned __int8 *)pMarshalInfo.Level1.Buffer + pMarshalInfo.Level1.BufferSize;
  if ( a2 < pMarshalInfo.Level1.Buffer || a2 > v10 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Buffer pointer out of bounds");
  v11 = a4 != 0 ? 7 : 3;
  v12 = v11 & (v11 - ((unsigned int)a2 & v11) + 1);
  if ( (int)v10 - (int)a2 < (unsigned int)v12 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v12);
  v13 = &a2[v12];
  v14 = v10 - v13;
  if ( a4 )
  {
    if ( v14 < 8 )
      goto LABEL_65;
    v28 = (char *)(v13 + 8);
    if ( !*(_QWORD *)v13 )
      return;
    if ( (unsigned __int64)(v10 - (unsigned __int8 *)v28) < 8 )
      goto LABEL_65;
    v29 = *(_QWORD *)v28;
    v17 = (unsigned __int16 *)(v13 + 16);
    v16 = v29;
    if ( (unsigned int)v29 != v29 )
      goto LABEL_36;
  }
  else
  {
    if ( v14 < 4 )
      goto LABEL_65;
    v15 = (char *)(v13 + 4);
    if ( !*(_DWORD *)v13 )
      return;
    if ( (unsigned __int64)(v10 - (unsigned __int8 *)v15) < 4 )
      goto LABEL_65;
    v16 = *(_DWORD *)v15;
    v17 = (unsigned __int16 *)(v13 + 8);
  }
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)v17) < 2 )
    goto LABEL_65;
  v18 = *v17;
  v19 = v17 + 1;
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)v19) < 2 )
    goto LABEL_65;
  v20 = *v19;
  v54 = *v19;
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)(v19 + 1)) < 4 )
    goto LABEL_65;
  v21 = *(_DWORD *)(v19 + 1);
  v9 = (unsigned __int64)(v19 + 3);
  v55[0] = v19 + 3;
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)(v19 + 3)) < 4 )
    goto LABEL_65;
  v22 = v19 + 5;
  v55[0] = v9 + 4;
  if ( a4 )
  {
    v30 = -(int)v22 & 7;
    if ( (int)v10 - (int)v22 < v30 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v30);
    v22 = (_DWORD *)((char *)v22 + v30);
  }
  v59 = *(_DWORD *)v9;
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)v22) < 4 )
    goto LABEL_65;
  v23 = *(unsigned __int16 *)v22;
  v24 = (char *)(v22 + 1);
  if ( v23 != *v22 )
    goto LABEL_36;
  if ( a4 )
  {
    v31 = -(int)v24 & 7;
    if ( (int)v10 - (int)v24 < (unsigned int)v31 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v31);
    v32 = &v24[v31];
    if ( (unsigned __int64)(v10 - (unsigned __int8 *)v32) >= 8 )
    {
      v9 = (unsigned __int64)(v32 + 8);
      *(_QWORD *)v58 = *(unsigned int *)v32;
      if ( *(_QWORD *)v58 == *(_QWORD *)v32 )
        goto LABEL_21;
LABEL_36:
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected cast truncation", v9);
    }
LABEL_65:
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Read()");
  }
  if ( (unsigned __int64)(v10 - (unsigned __int8 *)v24) < 4 )
    goto LABEL_65;
  v9 = (unsigned __int64)(v22 + 2);
  *(_QWORD *)v58 = *(unsigned int *)v24;
LABEL_21:
  v25 = a4 != 0 ? 8 : 4;
  if ( (int)v10 - (int)v9 < v25 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v25);
  v26 = (char *)(v9 + v25);
  v55[0] = v26;
  if ( (_WORD)v23 == 0x800D )
  {
    if ( (unsigned int)((_DWORD)v10 - (_DWORD)v26) < 0x10 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", 16);
    v26 += 16;
    v33 = v20 & 0xF60;
    v9 = v20;
    if ( v33 == 576 )
    {
      v27 = 13;
    }
    else
    {
      if ( v33 != 1088 )
        SafeBuffer::RaiseShieldException(
          (SafeBuffer *)v55,
          "Buffer inconsistency: sfDiscr == SF_HAVEIID but fFeatures (%lxh) is neither FADF_UNKNOWN|FADF_HAVEIID nor FADF"
          "_DISPATCH|FADF_HAVEIID",
          v20);
      v27 = 9;
    }
  }
  else
  {
    v27 = (unsigned __int16)v23;
  }
  v57 = v18;
  if ( v16 != v18 || !v18 )
    goto LABEL_25;
  v34 = 1;
  do
  {
    if ( (unsigned __int64)(v10 - (unsigned __int8 *)v26) < 8 )
      goto LABEL_65;
    v35 = *(_QWORD *)v26;
    v26 += 8;
    if ( (_DWORD)v35 )
    {
      if ( 0xFFFFFFFF / (unsigned int)v35 < v34 )
        SafeBuffer::RaiseShieldException(
          (SafeBuffer *)v55,
          "Input value(s) too large: causes addition overflow (%lu * %lu)",
          v34,
          v35);
      if ( !(unsigned int)SBGetConfigValue(1, 0xFFFFFFFF % (unsigned int)v35, v9, 0)
        && v34 * (unsigned int)v35 >= 0x7FFFF000 )
      {
        SafeBuffer::RaiseShieldException(
          (SafeBuffer *)v55,
          "Input value(s) too large: suspected DoS (%lu * %lu)",
          v34,
          v35);
      }
      v34 *= (_DWORD)v35;
    }
    else
    {
      v34 = 0;
    }
    ++v7;
  }
  while ( v7 < v57 );
  v36 = a4 != 0 ? 8 : 4;
  if ( (int)v10 - (int)v26 < v36 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v36);
  v37 = &v26[v36];
  if ( (unsigned __int16)v27 > 0x24u )
    goto LABEL_25;
  v38 = 0x100011330CLL;
  if ( !_bittest64(&v38, v27) || (v54 & 0xC008) != 0 )
    goto LABEL_25;
  v39 = v54 & 0xF20;
  v40 = v54 & 0xE0;
  switch ( (unsigned __int16)v27 )
  {
    case 8u:
      v50 = 256;
LABEL_109:
      v41 = v39 == v50;
      goto LABEL_110;
    case 9u:
      v52 = 1024;
      goto LABEL_114;
    case 0xCu:
      v50 = 2048;
      goto LABEL_109;
  }
  if ( (unsigned __int16)v27 != 13 )
  {
    if ( (unsigned __int16)v27 == 36 )
    {
      if ( v39 != 32 )
        goto LABEL_25;
      v51 = -33;
      goto LABEL_66;
    }
    v41 = v39 == 0;
LABEL_110:
    if ( !v41 )
      goto LABEL_25;
    v51 = -129;
LABEL_66:
    if ( (v40 & (unsigned __int16)v51) != 0 )
      goto LABEL_25;
    goto LABEL_67;
  }
  v52 = 512;
LABEL_114:
  if ( v39 != v52 || (v54 & 0x20) != 0 || v40 == 192 )
    goto LABEL_25;
LABEL_67:
  if ( (unsigned __int16)v27 > 0x14u || (v42 = 1114124, !_bittest(&v42, v27)) )
  {
    v49 = SafeBuffer::Mul((SafeBuffer *)v55, a4 != 0 ? 8 : 4, v58[0]);
    if ( (int)v10 - (int)v37 < v49 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unexpected end of buffer during BUFFER.Increment(%lu)", v49);
    v37 += v49;
  }
  v55[0] = v37;
  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  v43 = NdrGetUserMarshalInfo(pFlags, 1u, &pMarshalInfo);
  if ( v43 )
    RpcRaiseException(v43);
  v55[1] = pMarshalInfo.Level1.Buffer;
  BufferSize = pMarshalInfo.Level1.BufferSize;
  v55[2] = (char *)pMarshalInfo.Level1.Buffer + pMarshalInfo.Level1.BufferSize;
  if ( v37 < pMarshalInfo.Level1.Buffer || v37 > (char *)pMarshalInfo.Level1.Buffer + pMarshalInfo.Level1.BufferSize )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Buffer pointer out of bounds");
  RecordSize = v21;
  if ( (unsigned __int16)v27 > 0xCu )
  {
    switch ( (unsigned __int16)v27 )
    {
      case 0x14u:
        v47 = v21 == 8;
        break;
      case 0x10u:
        v47 = v21 == 1;
        break;
      case 0xDu:
LABEL_81:
        RecordSize = 8;
        if ( ((v21 - 4) & 0xFFFFFFFB) == 0 )
          goto LABEL_82;
        goto LABEL_78;
      case 0x24u:
        RecordSize = SafeArray_RetrieveRecordSize(pFlags, (struct SafeBuffer *)v55, a4);
        goto LABEL_82;
      default:
LABEL_107:
        SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "Unknown sfdiscr (%lu)", (unsigned __int16)v27);
    }
  }
  else
  {
    if ( (unsigned __int16)v27 == 12 )
    {
      if ( ((v21 - 16) & 0xFFFFFFF7) == 0 )
      {
        RecordSize = 24;
        goto LABEL_82;
      }
LABEL_78:
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, qword_1800AD360);
    }
    if ( (unsigned __int16)v27 != 2 )
    {
      switch ( (unsigned __int16)v27 )
      {
        case 3u:
          v47 = v21 == 4;
          goto LABEL_77;
        case 8u:
        case 9u:
          goto LABEL_81;
        case 0xAu:
          SafeBuffer::RaiseShieldException((SafeBuffer *)v55, "SF_ERROR not a valid sfType.");
      }
      goto LABEL_107;
    }
    v47 = v21 == 2;
  }
LABEL_77:
  if ( !v47 )
    goto LABEL_78;
LABEL_82:
  if ( (v54 & 0x80u) == 0 )
  {
    if ( HIWORD(v59) )
      goto LABEL_25;
  }
  else
  {
    SafeArray_ValidateVt((struct SafeBuffer *)v55, HIWORD(v59), v27);
  }
  if ( RecordSize )
  {
    if ( 0xFFFFFFFF / RecordSize < v34 )
      SafeBuffer::RaiseShieldException(
        (SafeBuffer *)v55,
        "Input value(s) too large: causes addition overflow (%lu * %lu)",
        v34,
        RecordSize);
    if ( !(unsigned int)SBGetConfigValue(1, 0xFFFFFFFF % RecordSize, v44, v45) && v34 * RecordSize >= 0x7FFFF000 )
      SafeBuffer::RaiseShieldException(
        (SafeBuffer *)v55,
        "Input value(s) too large: suspected DoS (%lu * %lu)",
        v34,
        RecordSize);
  }
  if ( (_WORD)v27 == 36 )
    v48 = v58[0] == 1;
  else
    v48 = v58[0] == v34;
  if ( !v48 )
LABEL_25:
    SafeBuffer::RaiseShieldException((SafeBuffer *)v55, qword_1800AD360);
  if ( a3 )
  {
    fFeatures = a3->fFeatures;
    if ( fFeatures != v54 && (((unsigned __int8)fFeatures ^ (unsigned __int8)v54) & 7) != 0 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, 0x80020010, "Callee cannot change the allocation features.");
    if ( a3->cDims != v57 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v55, 0x80020010, "Callee cannot change the rank.");
    if ( (v54 & 0x20) != 0 && (a3->fFeatures & 0x20) == 0 )
      SafeBuffer::RaiseShieldException(
        (SafeBuffer *)v55,
        0x80020010,
        "Callee cannot turn a non-record SAFEARRAY into a record SAFEARRAY.");
  }
}

```

## disassembly

```asm
0x18001ea5c  mov     rax, rsp
0x18001ea5f  mov     [rax+10h], rbx
0x18001ea63  mov     [rax+20h], r9d
0x18001ea67  mov     [rax+18h], r8
0x18001ea6b  mov     [rax+8], rcx
0x18001ea6f  push    rbp
0x18001ea70  push    rsi
0x18001ea71  push    rdi
0x18001ea72  push    r12
0x18001ea74  push    r13
0x18001ea76  push    r14
0x18001ea78  push    r15
0x18001ea7a  lea     rbp, [rax-5Fh]
0x18001ea7e  sub     rsp, 0C0h
0x18001ea85  mov     esi, r9d
0x18001ea88  mov     rbx, rdx
0x18001ea8b  mov     rdi, rcx
0x18001ea8e  call    ?ShieldActivated@@YAHXZ; ShieldActivated(void)
0x18001ea93  xor     r15d, r15d
0x18001ea96  test    eax, eax
0x18001ea98  jz      loc_18001ED01
0x18001ea9e  xor     edx, edx; Val
0x18001eaa0  lea     r8d, [r15+58h]; Size
0x18001eaa4  lea     rcx, [rbp+57h+pMarshalInfo]; void *
0x18001eaa8  call    memset_0
0x18001eaad  lea     r8, [rbp+57h+pMarshalInfo]; pMarshalInfo
0x18001eab1  mov     rcx, rdi; pFlags
0x18001eab4  lea     edx, [r15+1]; InformationLevel
0x18001eab8  call    cs:__imp_NdrGetUserMarshalInfo
0x18001eabe  test    eax, eax
0x18001eac0  jnz     loc_18001F11D
0x18001eac6  mov     edi, dword ptr [rbp+57h+pMarshalInfo.8+8]
0x18001eac9  add     rdi, qword ptr [rbp+57h+pMarshalInfo.8]
0x18001eacd  cmp     rbx, qword ptr [rbp+57h+pMarshalInfo.8]
0x18001ead1  jb      loc_18001F2AD
0x18001ead7  cmp     rbx, rdi
0x18001eada  ja      loc_18001F2AD
0x18001eae0  mov     eax, esi
0x18001eae2  lea     r14d, [r15+4]
0x18001eae6  neg     eax
0x18001eae8  sbb     ecx, ecx
0x18001eaea  and     ecx, r14d
0x18001eaed  add     ecx, 3
0x18001eaf0  mov     eax, ecx
0x18001eaf2  mov     edx, ecx
0x18001eaf4  and     eax, ebx
0x18001eaf6  sub     edx, eax
0x18001eaf8  mov     eax, edi
0x18001eafa  inc     edx
0x18001eafc  sub     eax, ebx
0x18001eafe  and     edx, ecx
0x18001eb00  cmp     eax, edx
0x18001eb02  jb      loc_18001F126
0x18001eb08  add     rdx, rbx
0x18001eb0b  mov     rax, rdi
0x18001eb0e  sub     rax, rdx
0x18001eb11  test    esi, esi
0x18001eb13  jnz     loc_18001EC51
0x18001eb19  cmp     rax, r14
0x18001eb1c  jb      loc_18001EE8B
0x18001eb22  lea     rcx, [rdx+4]
0x18001eb26  cmp     [rdx], r15d
0x18001eb29  jz      loc_18001ED01
0x18001eb2f  mov     rax, rdi
0x18001eb32  sub     rax, rcx
0x18001eb35  cmp     rax, r14
0x18001eb38  jb      loc_18001EE8B
0x18001eb3e  mov     r10d, [rcx]
0x18001eb41  add     rcx, r14
0x18001eb44  mov     rax, rdi
0x18001eb47  sub     rax, rcx
0x18001eb4a  cmp     rax, 2
0x18001eb4e  jb      loc_18001EE8B
0x18001eb54  movzx   r11d, word ptr [rcx]
0x18001eb58  mov     rax, rdi
0x18001eb5b  add     rcx, 2
0x18001eb5f  sub     rax, rcx
0x18001eb62  cmp     rax, 2
0x18001eb66  jb      loc_18001EE8B
0x18001eb6c  movzx   ebx, word ptr [rcx]
0x18001eb6f  lea     r8, [rcx+2]
0x18001eb73  mov     rax, rdi
0x18001eb76  mov     [rbp+57h+var_D0], bx
0x18001eb7a  sub     rax, r8
0x18001eb7d  cmp     rax, r14
0x18001eb80  jb      loc_18001EE8B
0x18001eb86  mov     r13d, [r8]
0x18001eb89  mov     rax, rdi
0x18001eb8c  add     r8, r14
0x18001eb8f  sub     rax, r8
0x18001eb92  mov     [rbp+57h+var_C8], r8
0x18001eb96  cmp     rax, r14
0x18001eb99  jb      loc_18001EE8B
0x18001eb9f  lea     rcx, [r8+4]
0x18001eba3  mov     [rbp+57h+var_C8], rcx
0x18001eba7  test    esi, esi
0x18001eba9  jnz     loc_18001EC8D
0x18001ebaf  mov     eax, [r8]
0x18001ebb2  mov     [rbp+57h+var_98], eax
0x18001ebb5  mov     rax, rdi
0x18001ebb8  sub     rax, rcx
0x18001ebbb  cmp     rax, r14
0x18001ebbe  jb      loc_18001EE8B
0x18001ebc4  movzx   r9d, word ptr [rcx]
0x18001ebc8  lea     rdx, [rcx+4]
0x18001ebcc  cmp     r9d, [rcx]
0x18001ebcf  jnz     loc_18001ECE3
0x18001ebd5  test    esi, esi
0x18001ebd7  jnz     loc_18001ECAA
0x18001ebdd  mov     rax, rdi
0x18001ebe0  sub     rax, rdx
0x18001ebe3  cmp     rax, r14
0x18001ebe6  jb      loc_18001EE8B
0x18001ebec  mov     eax, [rdx]
0x18001ebee  lea     r8, [rdx+4]
0x18001ebf2  mov     qword ptr [rbp+57h+var_A0], rax
0x18001ebf6  mov     eax, esi
0x18001ebf8  neg     eax
0x18001ebfa  mov     eax, edi
0x18001ebfc  sbb     ecx, ecx
0x18001ebfe  sub     eax, r8d
0x18001ec01  and     ecx, r14d
0x18001ec04  add     ecx, r14d
0x18001ec07  cmp     eax, ecx
0x18001ec09  jb      loc_18001F162
0x18001ec0f  mov     r14d, ecx
0x18001ec12  mov     eax, 800Dh
0x18001ec17  add     r14, r8
0x18001ec1a  mov     ecx, 0Dh
0x18001ec1f  mov     [rbp+57h+var_C8], r14
0x18001ec23  cmp     r9w, ax
0x18001ec27  jz      loc_18001ED1C
0x18001ec2d  movzx   r12d, r9w
0x18001ec31  mov     eax, r11d
0x18001ec34  mov     [rbp+57h+var_A8], eax
0x18001ec37  cmp     r10d, r11d
0x18001ec3a  jz      loc_18001ED6B
0x18001ec40  lea     rdx, qword_1800AD360; char *
0x18001ec47  lea     rcx, [rbp+57h+var_C8]; this
0x18001ec4b  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001ec51  cmp     rax, 8
0x18001ec55  jb      loc_18001EE8B
0x18001ec5b  lea     rcx, [rdx+8]
0x18001ec5f  cmp     [rdx], r15
0x18001ec62  jz      loc_18001ED01
0x18001ec68  mov     rax, rdi
0x18001ec6b  sub     rax, rcx
0x18001ec6e  cmp     rax, 8
0x18001ec72  jb      loc_18001EE8B
0x18001ec78  mov     rax, [rcx]
0x18001ec7b  add     rcx, 8
0x18001ec7f  mov     r10d, eax
0x18001ec82  cmp     r10, rax
0x18001ec85  jz      loc_18001EB44
0x18001ec8b  jmp     short loc_18001ECE3
0x18001ec8d  mov     edx, ecx
0x18001ec8f  mov     eax, edi
0x18001ec91  neg     edx
0x18001ec93  sub     eax, ecx
0x18001ec95  and     edx, 7
0x18001ec98  cmp     eax, edx
0x18001ec9a  jb      loc_18001F13A
0x18001eca0  mov     eax, edx
0x18001eca2  add     rcx, rax
0x18001eca5  jmp     loc_18001EBAF
0x18001ecaa  mov     ecx, edx
0x18001ecac  mov     eax, edi
0x18001ecae  neg     ecx
0x18001ecb0  sub     eax, edx
0x18001ecb2  and     ecx, 7
0x18001ecb5  cmp     eax, ecx
0x18001ecb7  jb      loc_18001F14E
0x18001ecbd  add     rcx, rdx
0x18001ecc0  mov     rax, rdi
0x18001ecc3  sub     rax, rcx
0x18001ecc6  cmp     rax, 8
0x18001ecca  jb      loc_18001EE8B
0x18001ecd0  mov     edx, [rcx]
0x18001ecd2  lea     r8, [rcx+8]
0x18001ecd6  mov     qword ptr [rbp+57h+var_A0], rdx
0x18001ecda  cmp     rdx, [rcx]
0x18001ecdd  jz      loc_18001EBF6
0x18001ece3  lea     rdx, aUnexpectedCast; "Unexpected cast truncation"
0x18001ecea  lea     rcx, [rbp+57h+var_C8]; this
0x18001ecee  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001ecf4  mov     rcx, [rbp+57h+arg_10]
0x18001ecf8  test    rcx, rcx
0x18001ecfb  jnz     loc_18001F228
0x18001ed01  mov     rbx, [rsp+0F0h+arg_8]
0x18001ed09  add     rsp, 0C0h
0x18001ed10  pop     r15
0x18001ed12  pop     r14
0x18001ed14  pop     r13
0x18001ed16  pop     r12
0x18001ed18  pop     rdi
0x18001ed19  pop     rsi
0x18001ed1a  pop     rbp
0x18001ed1b  retn
0x18001ed1c  mov     eax, edi
0x18001ed1e  sub     eax, r14d
0x18001ed21  cmp     eax, 10h
0x18001ed24  jb      loc_18001F176
0x18001ed2a  mov     eax, ebx
0x18001ed2c  add     r14, 10h
0x18001ed30  and     eax, 0F60h
0x18001ed35  mov     r8d, ebx
0x18001ed38  cmp     eax, 240h
0x18001ed3d  jz      short loc_18001ED57
0x18001ed3f  cmp     eax, 440h
0x18001ed44  jz      short loc_18001ED60
0x18001ed46  lea     rdx, aBufferInconsis_0; "Buffer inconsistency: sfDiscr == SF_HAV"...
0x18001ed4d  lea     rcx, [rbp+57h+var_C8]; this
0x18001ed51  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001ed57  movzx   r12d, cx
0x18001ed5b  jmp     loc_18001EC31
0x18001ed60  mov     r12d, 9
0x18001ed66  jmp     loc_18001EC31
0x18001ed6b  test    eax, eax
0x18001ed6d  jz      loc_18001EC40
0x18001ed73  xor     r9d, r9d
0x18001ed76  mov     esi, 1
0x18001ed7b  test    eax, eax
0x18001ed7d  jz      short loc_18001EDDE
0x18001ed7f  mov     rax, rdi
0x18001ed82  sub     rax, r14
0x18001ed85  cmp     rax, 8
0x18001ed89  jb      loc_18001EE8B
0x18001ed8f  mov     rbx, [r14]
0x18001ed92  add     r14, 8
0x18001ed96  test    ebx, ebx
0x18001ed98  jz      loc_18001EE83
0x18001ed9e  xor     edx, edx
0x18001eda0  or      eax, 0FFFFFFFFh
0x18001eda3  div     ebx
0x18001eda5  cmp     eax, esi
0x18001eda7  jb      loc_18001F1A4
0x18001edad  mov     ecx, 1
0x18001edb2  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18001edb7  xor     r9d, r9d
0x18001edba  test    eax, eax
0x18001edbc  jnz     short loc_18001EDCE
0x18001edbe  mov     eax, ebx
0x18001edc0  imul    eax, esi
0x18001edc3  cmp     eax, 7FFFF000h
0x18001edc8  jnb     loc_18001F18D
0x18001edce  imul    esi, ebx
0x18001edd1  inc     r15d
0x18001edd4  cmp     r15d, [rbp+57h+var_A8]
0x18001edd8  jb      short loc_18001ED7F
0x18001edda  movzx   ebx, [rbp+57h+var_D0]
0x18001edde  mov     r15d, [rbp+57h+arg_18]
0x18001ede2  mov     eax, r15d
0x18001ede5  neg     eax
0x18001ede7  mov     eax, edi
0x18001ede9  sbb     ecx, ecx
0x18001edeb  sub     eax, r14d
0x18001edee  and     ecx, 4
0x18001edf1  add     ecx, 4
0x18001edf4  cmp     eax, ecx
0x18001edf6  jb      loc_18001F1BB
0x18001edfc  mov     eax, ecx
0x18001edfe  add     r14, rax
0x18001ee01  mov     eax, 24h ; '$'
0x18001ee06  cmp     r12w, ax
0x18001ee0a  ja      loc_18001EC40
0x18001ee10  mov     rcx, 100011330Ch
0x18001ee1a  bt      rcx, r12
0x18001ee1e  jnb     loc_18001EC40
0x18001ee24  movzx   eax, bx
0x18001ee27  test    eax, 0FFFFC008h
0x18001ee2c  jnz     loc_18001EC40
0x18001ee32  mov     eax, 0F20h
0x18001ee37  movzx   ecx, r12w
0x18001ee3b  movzx   edx, bx
0x18001ee3e  movzx   r8d, bx
0x18001ee42  and     dx, ax
0x18001ee45  mov     eax, 0E0h
0x18001ee4a  and     r8w, ax
0x18001ee4e  sub     ecx, 8
0x18001ee51  jz      loc_18001F0B2
0x18001ee57  sub     ecx, 1
0x18001ee5a  jz      loc_18001F0D1
0x18001ee60  sub     ecx, 3
0x18001ee63  jz      loc_18001F0CA
0x18001ee69  sub     ecx, 1
0x18001ee6c  jz      loc_18001F102
0x18001ee72  cmp     ecx, 17h
0x18001ee75  jz      loc_18001F109
0x18001ee7b  test    dx, dx
0x18001ee7e  jmp     loc_18001F0BA
0x18001ee83  mov     esi, r9d
0x18001ee86  jmp     loc_18001EDD1
0x18001ee8b  lea     rdx, aUnexpectedEndO; "Unexpected end of buffer during BUFFER."...
0x18001ee92  lea     rcx, [rbp+57h+var_C8]; this
0x18001ee96  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001ee9c  test    ax, r8w
0x18001eea0  jnz     loc_18001EC40
0x18001eea6  mov     eax, 14h
0x18001eeab  cmp     r12w, ax
0x18001eeaf  ja      loc_18001EFF8
  ... truncated ...
```
