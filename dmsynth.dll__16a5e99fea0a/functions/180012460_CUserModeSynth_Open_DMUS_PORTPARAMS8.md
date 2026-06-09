# CUserModeSynth::Open(_DMUS_PORTPARAMS8 *)

- ea: `0x180012460`
- end: `0x180012943`
- name: `?Open@CUserModeSynth@@UEAAJPEAU_DMUS_PORTPARAMS8@@@Z`
- size: `1251`
- prototype: `int(CUserModeSynth *__hidden this, struct _DMUS_PORTPARAMS8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180005a70`
- `0x180005f60`
- `0x1800060d0`
- `0x180006e50`
- `0x180006ec0`
- `0x1800073a0`
- `0x1800114b0`
- `0x180012460`
- `0x1800148d1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012768`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012768`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001273f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012853`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001273f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012853`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800127b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001291b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800127b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001291b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012926`

## pseudocode

```c
__int64 __fastcall CUserModeSynth::Open(CUserModeSynth *this, struct _DMUS_PORTPARAMS8 *a2)
{
  DWORD dwSize; // eax
  int v4; // edx
  DWORD v6; // r15d
  unsigned int v7; // r10d
  bool v8; // bl
  DWORD v9; // r14d
  DWORD dwChannelGroups; // r13d
  DWORD v11; // edi
  DWORD dwEffectFlags; // r12d
  int v13; // eax
  DWORD v14; // r11d
  DWORD dwValidParams; // r9d
  DWORD dwVoices; // ecx
  DWORD v17; // eax
  DWORD dwAudioChannels; // eax
  DWORD dwSampleRate; // ecx
  char v20; // al
  char v21; // al
  struct _RTL_CRITICAL_SECTION *v22; // r15
  CSynth **v23; // rsi
  CSynth *v24; // rax
  CSynth *v25; // r14
  int v26; // edi
  int v27; // r12d
  __int16 v28; // r13
  CSynth *v29; // rcx
  CSynth *v30; // rcx
  CSynth *v31; // rcx
  unsigned int *v32; // [rsp+20h] [rbp-78h]
  unsigned int *v33; // [rsp+28h] [rbp-70h]
  _DWORD Src[2]; // [rsp+30h] [rbp-68h] BYREF
  int v35; // [rsp+38h] [rbp-60h]
  __int64 v36; // [rsp+3Ch] [rbp-5Ch]
  __int64 v37; // [rsp+44h] [rbp-54h]
  __int64 v38; // [rsp+4Ch] [rbp-4Ch]
  CUserModeSynth *v39; // [rsp+A0h] [rbp+8h]
  char v40; // [rsp+A8h] [rbp+10h]
  __int16 v41; // [rsp+A8h] [rbp+10h]
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+B8h] [rbp+20h]

  v39 = this;
  if ( a2 )
  {
    dwSize = a2->dwSize;
    if ( a2->dwSize == 32 )
    {
      v4 = 7;
    }
    else
    {
      if ( dwSize == 36 )
      {
        v6 = 36;
        v7 = 36;
        v4 = 8;
        goto LABEL_11;
      }
      v4 = 7;
      if ( dwSize <= 0x20 )
        return 2147942487LL;
    }
    v7 = 32;
  }
  else
  {
    v7 = 0;
    v4 = 0;
  }
  v6 = 36;
LABEL_11:
  v8 = 0;
  v40 = 0;
  v38 = 0;
  Src[0] = 36;
  v35 = 32;
  v9 = 2;
  dwChannelGroups = 2;
  v36 = 0x200000002LL;
  v11 = 22050;
  v37 = 0x100005622LL;
  LOBYTE(dwEffectFlags) = 1;
  v13 = 111;
  if ( !a2 )
    goto LABEL_67;
  v14 = a2->dwSize;
  if ( a2->dwSize >= 0x24 )
    v13 = 239;
  Src[1] = v13;
  dwValidParams = a2->dwValidParams;
  if ( (dwValidParams & 1) != 0 )
  {
    dwVoices = a2->dwVoices;
    if ( dwVoices )
    {
      v17 = 1000;
      if ( dwVoices <= 0x3E8 )
        v17 = a2->dwVoices;
      v35 = v17;
      v8 = dwVoices > 0x3E8;
    }
    else
    {
      v8 = 1;
      v35 = 1;
    }
    v40 = v8;
  }
  if ( (dwValidParams & 2) != 0 )
  {
    dwChannelGroups = a2->dwChannelGroups;
    if ( dwChannelGroups )
    {
      if ( dwChannelGroups <= 0x3E8 )
      {
        LODWORD(v36) = a2->dwChannelGroups;
        goto LABEL_28;
      }
      dwChannelGroups = 1000;
      LODWORD(v36) = 1000;
    }
    else
    {
      dwChannelGroups = 1;
      LODWORD(v36) = 1;
    }
    v8 = 1;
    v40 = 1;
  }
LABEL_28:
  if ( (dwValidParams & 4) != 0 )
  {
    dwAudioChannels = a2->dwAudioChannels;
    if ( dwAudioChannels )
    {
      if ( dwAudioChannels <= 2 )
      {
        v9 = a2->dwAudioChannels;
        HIDWORD(v36) = v9;
        goto LABEL_35;
      }
      HIDWORD(v36) = 2;
    }
    else
    {
      v9 = 1;
      HIDWORD(v36) = 1;
    }
    v8 = 1;
    v40 = 1;
  }
LABEL_35:
  if ( (dwValidParams & 8) != 0 )
  {
    dwSampleRate = a2->dwSampleRate;
    if ( v4 == 7 )
    {
      if ( dwSampleRate <= 0x7530 )
      {
        v20 = v8;
        if ( dwSampleRate <= 0x3A98 )
        {
          v11 = 11025;
          if ( dwSampleRate != 11025 )
            v20 = 1;
          v8 = v20;
          v40 = v20;
          LODWORD(v37) = 11025;
        }
        else
        {
          if ( dwSampleRate != 22050 )
            v20 = 1;
          v8 = v20;
          v40 = v20;
          LODWORD(v37) = 22050;
        }
      }
      else
      {
        v11 = 44100;
        if ( dwSampleRate != 44100 )
          v8 = 1;
        v40 = v8;
        LODWORD(v37) = 44100;
      }
    }
    else
    {
      v11 = 96000;
      if ( dwSampleRate <= 0x17700 )
      {
        v11 = 11025;
        if ( dwSampleRate >= 0x2B11 )
        {
          v11 = a2->dwSampleRate;
          LODWORD(v37) = v11;
        }
        else
        {
          v8 = 1;
          v40 = 1;
          LODWORD(v37) = 11025;
        }
      }
      else
      {
        v8 = 1;
        v40 = 1;
        LODWORD(v37) = 96000;
      }
    }
  }
  if ( (dwValidParams & 0x20) != 0 )
  {
    dwEffectFlags = a2->dwEffectFlags;
    if ( (dwEffectFlags & 0xFFFFFFFE) != 0 )
    {
      v8 = 1;
      v40 = 1;
      dwEffectFlags = a2->dwEffectFlags & 1;
      a2->dwEffectFlags = dwEffectFlags;
    }
    HIDWORD(v37) = dwEffectFlags;
  }
  if ( (dwValidParams & 0x40) != 0 )
  {
    v21 = v8;
    if ( a2->fShare )
      v21 = 1;
    v8 = v21;
    v40 = v21;
  }
  if ( (dwValidParams & 0x80u) != 0 && v14 >= 0x24 )
    HIDWORD(v38) = a2->dwFeatures;
  if ( v7 < 0x24 )
    v6 = v7;
  memcpy_0(a2, Src, v6);
  a2->dwSize = v6;
  this = v39;
LABEL_67:
  v33 = (unsigned int *)((char *)this + 68);
  *((_DWORD *)this + 17) = v11;
  *((_DWORD *)this + 18) = v9;
  v32 = (unsigned int *)((char *)this + 76);
  *((_DWORD *)this + 19) = v9 != 1;
  v22 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v42 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v23 = (CSynth **)((char *)v39 + 56);
  if ( *((_QWORD *)v39 + 7) )
  {
    LeaveCriticalSection(v22);
    return (unsigned int)-2005397201;
  }
  try
  {
    v24 = (CSynth *)malloc(0x448u);
    if ( v24 )
      v24 = CSynth::CSynth(v24);
    *v23 = v24;
  }
  catch ( ... )
  {
    *((_QWORD *)v39 + 7) = 0;
    v8 = v40;
    LOBYTE(dwEffectFlags) = BYTE4(v37);
    dwChannelGroups = v36;
    v23 = (CSynth **)((char *)v39 + 56);
    v22 = v42;
  }
  v25 = *v23;
  if ( *v23 )
  {
    if ( dwChannelGroups - 1 > 0x3E7 )
    {
      v26 = -2147024809;
    }
    else
    {
      if ( !*((_QWORD *)v25 + 129) )
      {
        v27 = dwEffectFlags & 1;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 1048));
        v26 = CSynth::SetNumChannelGroups(v25, dwChannelGroups);
        if ( v26 >= 0 )
        {
          v41 = v35;
          if ( (__int16)v35 / 4 >= 4 )
            v28 = (__int16)v35 / 4;
          else
            v28 = 4;
          if ( (__int16)v35 < 1 )
            v41 = 1;
          if ( !v28 )
            v28 = 1;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 1048));
          *((_WORD *)v25 + 36) = CSynth::ChangeVoiceCount(v29, (CSynth *)((char *)v25 + 48), *((_WORD *)v25 + 36), v41);
          *((_WORD *)v25 + 37) = CSynth::ChangeVoiceCount(v30, (CSynth *)((char *)v25 + 56), *((_WORD *)v25 + 37), v28);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 1048));
        }
        CSynth::SetReverbActive(v25, v27);
        *((_DWORD *)v25 + 44) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 1048));
        v31 = *v23;
        if ( v26 >= 0 )
        {
          CSynth::SetGainAdjust(v31, *((_DWORD *)v39 + 22));
          CSynth::Activate(*v23, *v33, *v32);
          LeaveCriticalSection(v22);
          if ( v8 )
            return 1;
          return (unsigned int)v26;
        }
        goto LABEL_92;
      }
      v26 = -2147467259;
    }
    v31 = *v23;
LABEL_92:
    if ( v31 )
      CSynth::`scalar deleting destructor'(v31);
    *v23 = 0;
    LeaveCriticalSection(v22);
    return (unsigned int)v26;
  }
  v26 = -2147024882;
  LeaveCriticalSection(v22);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180012460  mov     [rsp+arg_0], rcx
0x180012465  push    rbx
0x180012466  push    rsi
0x180012467  push    rdi
0x180012468  push    r12
0x18001246a  push    r13
0x18001246c  push    r14
0x18001246e  push    r15
0x180012470  sub     rsp, 60h
0x180012474  mov     rsi, rdx
0x180012477  test    rdx, rdx
0x18001247a  jz      short loc_1800124C4
0x18001247c  mov     eax, [rdx]
0x18001247e  cmp     eax, 20h ; ' '
0x180012481  jz      short loc_1800124B7
0x180012483  cmp     eax, 24h ; '$'
0x180012486  jz      short loc_1800124A7
0x180012488  mov     edx, 7
0x18001248d  cmp     eax, 20h ; ' '
0x180012490  ja      short loc_1800124BC
0x180012492  mov     eax, 80070057h
0x180012497  add     rsp, 60h
0x18001249b  pop     r15
0x18001249d  pop     r14
0x18001249f  pop     r13
0x1800124a1  pop     r12
0x1800124a3  pop     rdi
0x1800124a4  pop     rsi
0x1800124a5  pop     rbx
0x1800124a6  retn
0x1800124a7  mov     r15d, 24h ; '$'
0x1800124ad  mov     r10d, r15d
0x1800124b0  mov     edx, 8
0x1800124b5  jmp     short loc_1800124CF
0x1800124b7  mov     edx, 7
0x1800124bc  mov     r10d, 20h ; ' '
0x1800124c2  jmp     short loc_1800124C9
0x1800124c4  xor     r10d, r10d
0x1800124c7  xor     edx, edx
0x1800124c9  mov     r15d, 24h ; '$'
0x1800124cf  xor     bl, bl
0x1800124d1  mov     byte ptr [rsp+98h+arg_8], bl
0x1800124d8  xorps   xmm0, xmm0
0x1800124db  movdqu  [rsp+98h+var_5C], xmm0
0x1800124e1  mov     [rsp+98h+var_4C], 0
0x1800124ea  mov     [rsp+98h+Src], r15d
0x1800124ef  mov     [rsp+98h+var_60], 20h ; ' '
0x1800124f7  mov     r14d, 2
0x1800124fd  mov     r13d, r14d
0x180012500  mov     dword ptr [rsp+98h+var_5C], r14d
0x180012505  mov     dword ptr [rsp+98h+var_5C+4], r14d
0x18001250a  mov     edi, 5622h
0x18001250f  mov     dword ptr [rsp+98h+var_5C+8], edi
0x180012513  mov     r8d, 1
0x180012519  mov     r12d, r8d
0x18001251c  mov     dword ptr [rsp+98h+var_5C+0Ch], r8d
0x180012521  mov     eax, 6Fh ; 'o'
0x180012526  test    rsi, rsi
0x180012529  jz      loc_18001270D
0x18001252f  mov     r11d, [rsi]
0x180012532  mov     ecx, 0EFh
0x180012537  cmp     r11d, 24h ; '$'
0x18001253b  cmovnb  eax, ecx
0x18001253e  mov     [rsp+98h+var_64], eax
0x180012542  mov     r9d, [rsi+4]
0x180012546  test    r8b, r9b
0x180012549  jz      short loc_180012575
0x18001254b  mov     ecx, [rsi+8]
0x18001254e  test    ecx, ecx
0x180012550  jz      short loc_180012565
0x180012552  mov     eax, 3E8h
0x180012557  cmp     ecx, eax
0x180012559  cmovbe  eax, ecx
0x18001255c  mov     [rsp+98h+var_60], eax
0x180012560  setnbe  bl
0x180012563  jmp     short loc_18001256E
0x180012565  movzx   ebx, r8b
0x180012569  mov     [rsp+98h+var_60], r8d
0x18001256e  mov     byte ptr [rsp+98h+arg_8], bl
0x180012575  test    r13b, r9b
0x180012578  jz      short loc_1800125B3
0x18001257a  mov     r13d, [rsi+0Ch]
0x18001257e  test    r13d, r13d
0x180012581  jz      short loc_1800125A0
0x180012583  cmp     r13d, 3E8h
0x18001258a  ja      short loc_180012593
0x18001258c  mov     dword ptr [rsp+98h+var_5C], r13d
0x180012591  jmp     short loc_1800125B3
0x180012593  mov     r13d, 3E8h
0x180012599  mov     dword ptr [rsp+98h+var_5C], r13d
0x18001259e  jmp     short loc_1800125A8
0x1800125a0  mov     r13d, r8d
0x1800125a3  mov     dword ptr [rsp+98h+var_5C], r8d
0x1800125a8  movzx   ebx, r8b
0x1800125ac  mov     byte ptr [rsp+98h+arg_8], bl
0x1800125b3  test    r9b, 4
0x1800125b7  jz      short loc_1800125E8
0x1800125b9  mov     eax, [rsi+10h]
0x1800125bc  test    eax, eax
0x1800125be  jz      short loc_1800125D5
0x1800125c0  cmp     eax, r14d
0x1800125c3  ja      short loc_1800125CE
0x1800125c5  mov     r14d, eax
0x1800125c8  mov     dword ptr [rsp+98h+var_5C+4], eax
0x1800125cc  jmp     short loc_1800125E8
0x1800125ce  mov     dword ptr [rsp+98h+var_5C+4], r14d
0x1800125d3  jmp     short loc_1800125DD
0x1800125d5  mov     r14d, r8d
0x1800125d8  mov     dword ptr [rsp+98h+var_5C+4], r8d
0x1800125dd  movzx   ebx, r8b
0x1800125e1  mov     byte ptr [rsp+98h+arg_8], bl
0x1800125e8  test    r9b, 8
0x1800125ec  jz      loc_180012693
0x1800125f2  mov     ecx, [rsi+14h]
0x1800125f5  cmp     edx, 7
0x1800125f8  jnz     short loc_180012659
0x1800125fa  cmp     ecx, 7530h
0x180012600  jbe     short loc_18001261D
0x180012602  movzx   ebx, bl
0x180012605  mov     edi, 0AC44h
0x18001260a  cmp     ecx, edi
0x18001260c  cmovnz  ebx, r8d
0x180012610  mov     byte ptr [rsp+98h+arg_8], bl
0x180012617  mov     dword ptr [rsp+98h+var_5C+8], edi
0x18001261b  jmp     short loc_180012693
0x18001261d  movzx   eax, bl
0x180012620  cmp     ecx, 3A98h
0x180012626  jbe     short loc_18001263E
0x180012628  cmp     ecx, edi
0x18001262a  cmovnz  eax, r8d
0x18001262e  movzx   ebx, al
0x180012631  mov     byte ptr [rsp+98h+arg_8], al
0x180012638  mov     dword ptr [rsp+98h+var_5C+8], edi
0x18001263c  jmp     short loc_180012693
0x18001263e  mov     edi, 2B11h
0x180012643  cmp     ecx, edi
0x180012645  cmovnz  eax, r8d
0x180012649  movzx   ebx, al
0x18001264c  mov     byte ptr [rsp+98h+arg_8], al
0x180012653  mov     dword ptr [rsp+98h+var_5C+8], edi
0x180012657  jmp     short loc_180012693
0x180012659  mov     edi, 17700h
0x18001265e  cmp     ecx, edi
0x180012660  jbe     short loc_180012673
0x180012662  movzx   ebx, r8b
0x180012666  mov     byte ptr [rsp+98h+arg_8], bl
0x18001266d  mov     dword ptr [rsp+98h+var_5C+8], edi
0x180012671  jmp     short loc_180012693
0x180012673  mov     edi, 2B11h
0x180012678  cmp     ecx, edi
0x18001267a  jnb     short loc_18001268D
0x18001267c  movzx   ebx, r8b
0x180012680  mov     byte ptr [rsp+98h+arg_8], bl
0x180012687  mov     dword ptr [rsp+98h+var_5C+8], edi
0x18001268b  jmp     short loc_180012693
0x18001268d  mov     edi, ecx
0x18001268f  mov     dword ptr [rsp+98h+var_5C+8], ecx
0x180012693  test    r9b, 20h
0x180012697  jz      short loc_1800126BD
0x180012699  mov     r12d, [rsi+18h]
0x18001269d  test    r12d, 0FFFFFFFEh
0x1800126a4  jz      short loc_1800126B8
0x1800126a6  movzx   ebx, r8b
0x1800126aa  mov     byte ptr [rsp+98h+arg_8], bl
0x1800126b1  and     r12d, r8d
0x1800126b4  mov     [rsi+18h], r12d
0x1800126b8  mov     dword ptr [rsp+98h+var_5C+0Ch], r12d
0x1800126bd  test    r9b, 40h
0x1800126c1  jz      short loc_1800126D8
0x1800126c3  movzx   eax, bl
0x1800126c6  cmp     dword ptr [rsi+1Ch], 0
0x1800126ca  cmovnz  eax, r8d
0x1800126ce  movzx   ebx, al
0x1800126d1  mov     byte ptr [rsp+98h+arg_8], al
0x1800126d8  test    r9b, r9b
0x1800126db  jns     short loc_1800126EA
0x1800126dd  cmp     r11d, 24h ; '$'
0x1800126e1  jb      short loc_1800126EA
0x1800126e3  mov     eax, [rsi+20h]
0x1800126e6  mov     dword ptr [rsp+98h+var_4C+4], eax
0x1800126ea  cmp     r10d, 24h ; '$'
0x1800126ee  cmovb   r15d, r10d
0x1800126f2  mov     r8d, r15d; Size
0x1800126f5  lea     rdx, [rsp+98h+Src]; Src
0x1800126fa  mov     rcx, rsi; void *
0x1800126fd  call    memcpy_0
0x180012702  mov     [rsi], r15d
0x180012705  mov     rcx, [rsp+98h+arg_0]
0x18001270d  lea     rax, [rcx+44h]
0x180012711  mov     [rsp+98h+var_70], rax
0x180012716  mov     [rax], edi
0x180012718  mov     [rcx+48h], r14d
0x18001271c  lea     rdx, [rcx+4Ch]
0x180012720  mov     [rsp+98h+var_78], rdx
0x180012725  xor     eax, eax
0x180012727  cmp     r14d, 1
0x18001272b  setnz   al
0x18001272e  mov     [rdx], eax
0x180012730  lea     r15, [rcx+60h]
0x180012734  mov     [rsp+98h+arg_18], r15
0x18001273c  mov     rcx, r15; lpCriticalSection
0x18001273f  call    cs:__imp_EnterCriticalSection
0x180012745  mov     rsi, [rsp+98h+arg_0]
0x18001274d  add     rsi, 38h ; '8'
0x180012751  mov     [rsp+98h+arg_10], rsi
0x180012759  cmp     qword ptr [rsi], 0
0x18001275d  jnz     loc_180012923
0x180012763  mov     ecx, 448h; Size
0x180012768  call    cs:__imp_malloc
0x18001276e  test    rax, rax
0x180012771  jz      short loc_18001277B
0x180012773  mov     rcx, rax; this
0x180012776  call    ??0CSynth@@QEAA@XZ; CSynth::CSynth(void)
0x18001277b  mov     [rsi], rax
0x18001277e  jmp     short loc_1800127A2
0x180012780  movzx   ebx, byte ptr [rsp+98h+arg_8]
0x180012788  mov     r12d, dword ptr [rsp+98h+var_5C+0Ch]
0x18001278d  mov     r13d, dword ptr [rsp+98h+var_5C]
0x180012792  mov     rsi, [rsp+98h+arg_10]
0x18001279a  mov     r15, [rsp+98h+arg_18]
0x1800127a2  mov     r14, [rsi]
0x1800127a5  test    r14, r14
0x1800127a8  jnz     short loc_1800127BD
0x1800127aa  mov     edi, 8007000Eh
0x1800127af  mov     rcx, r15; lpCriticalSection
0x1800127b2  call    cs:__imp_LeaveCriticalSection
0x1800127b8  jmp     loc_180012931
0x1800127bd  lea     eax, [r13-1]
0x1800127c1  cmp     eax, 3E7h
0x1800127c6  ja      loc_1800128FF
0x1800127cc  cmp     qword ptr [r14+408h], 0
0x1800127d4  jz      short loc_1800127E0
0x1800127d6  mov     edi, 80004005h
0x1800127db  jmp     loc_180012904
0x1800127e0  and     r12d, 1
0x1800127e4  lea     rcx, [r14+418h]; lpCriticalSection
0x1800127eb  call    cs:__imp_EnterCriticalSection
0x1800127f1  mov     edx, r13d; unsigned int
0x1800127f4  mov     rcx, r14; this
0x1800127f7  call    ?SetNumChannelGroups@CSynth@@QEAAJK@Z; CSynth::SetNumChannelGroups(ulong)
0x1800127fc  mov     edi, eax
0x1800127fe  test    eax, eax
0x180012800  js      loc_180012899
0x180012806  movsx   ecx, word ptr [rsp+98h+var_60]
0x18001280b  mov     [rsp+98h+arg_8], cx
0x180012813  mov     eax, ecx
0x180012815  cdq
0x180012816  and     edx, 3
0x180012819  add     eax, edx
0x18001281b  sar     eax, 2
0x18001281e  cmp     ax, 4
0x180012822  jge     short loc_18001282C
0x180012824  mov     r13d, 4
0x18001282a  jmp     short loc_180012830
0x18001282c  movzx   r13d, ax
0x180012830  mov     eax, 1
0x180012835  cmp     ecx, eax
0x180012837  jge     short loc_180012841
0x180012839  mov     [rsp+98h+arg_8], ax
0x180012841  cmp     r13w, 1
0x180012846  jnb     short loc_18001284C
0x180012848  movzx   r13d, ax
0x18001284c  lea     rcx, [r14+418h]; lpCriticalSection
0x180012853  call    cs:__imp_EnterCriticalSection
0x180012859  lea     rdx, [r14+30h]; struct CVoiceList *
0x18001285d  movzx   r9d, [rsp+98h+arg_8]; __int16
0x180012866  movzx   r8d, word ptr [r14+48h]; __int16
0x18001286b  call    ?ChangeVoiceCount@CSynth@@AEAAFPEAVCVoiceList@@FF@Z; CSynth::ChangeVoiceCount(CVoiceList *,short,short)
0x180012870  mov     [r14+48h], ax
0x180012875  lea     rdx, [r14+38h]; struct CVoiceList *
0x180012879  movzx   r9d, r13w; __int16
0x18001287d  movzx   r8d, word ptr [r14+4Ah]; __int16
0x180012882  call    ?ChangeVoiceCount@CSynth@@AEAAFPEAVCVoiceList@@FF@Z; CSynth::ChangeVoiceCount(CVoiceList *,short,short)
0x180012887  mov     [r14+4Ah], ax
0x18001288c  lea     rcx, [r14+418h]; lpCriticalSection
0x180012893  call    cs:__imp_LeaveCriticalSection
0x180012899  mov     edx, r12d; int
0x18001289c  mov     rcx, r14; this
0x18001289f  call    ?SetReverbActive@CSynth@@QEAAXH@Z; CSynth::SetReverbActive(int)
0x1800128a4  mov     dword ptr [r14+0B0h], 0
0x1800128af  lea     rcx, [r14+418h]; lpCriticalSection
0x1800128b6  call    cs:__imp_LeaveCriticalSection
0x1800128bc  mov     rcx, [rsi]; this
0x1800128bf  test    edi, edi
0x1800128c1  js      short loc_180012907
0x1800128c3  mov     rax, [rsp+98h+arg_0]
0x1800128cb  mov     edx, [rax+58h]; int
0x1800128ce  call    ?SetGainAdjust@CSynth@@QEAAXJ@Z; CSynth::SetGainAdjust(long)
0x1800128d3  mov     r8, [rsp+98h+var_78]
0x1800128d8  mov     r8d, [r8]; unsigned int
0x1800128db  mov     rdx, [rsp+98h+var_70]
0x1800128e0  mov     edx, [rdx]; unsigned int
0x1800128e2  mov     rcx, [rsi]; this
0x1800128e5  call    ?Activate@CSynth@@QEAAJKK@Z; CSynth::Activate(ulong,ulong)
0x1800128ea  mov     rcx, r15; lpCriticalSection
0x1800128ed  call    cs:__imp_LeaveCriticalSection
0x1800128f3  test    bl, bl
0x1800128f5  mov     eax, 1
0x1800128fa  cmovnz  edi, eax
0x1800128fd  jmp     short loc_180012931
  ... truncated ...
```
