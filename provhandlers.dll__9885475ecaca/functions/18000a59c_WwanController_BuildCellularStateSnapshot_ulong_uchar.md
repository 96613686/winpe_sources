# WwanController::BuildCellularStateSnapshot(ulong,uchar *)

- ea: `0x18000a59c`
- end: `0x18000ad2a`
- name: `?BuildCellularStateSnapshot@WwanController@@AEAAJKPEAE@Z`
- size: `1934`
- prototype: `__int64 __fastcall(WwanController *this, unsigned int, char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c26c`

## callees

- `0x18000108c`
- `0x180001424`
- `0x180001518`
- `0x180001608`
- `0x18000a59c`
- `0x18000dd78`
- `0x180037aa8`
- `0x18003b946`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a79d`
- `msvcrt!memcpy_s` at `0x18000a839`
- `msvcrt!memcpy_s` at `0x18000a865`
- `msvcrt!memcpy_s` at `0x18000a93c`
- `msvcrt!memcpy_s` at `0x18000a79d`
- `msvcrt!memcpy_s` at `0x18000a839`
- `msvcrt!memcpy_s` at `0x18000a865`
- `msvcrt!memcpy_s` at `0x18000a93c`

## string_xrefs

- `0x18000ab46`: `pModemStateHdr->numSIMSlot != sims.size()`

## pseudocode

```c
__int64 __fastcall WwanController::BuildCellularStateSnapshot(WwanController *this, unsigned int a2, char *a3)
{
  WwanController *v3; // r13
  unsigned __int8 *v4; // r15
  unsigned __int8 *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 **v8; // rbx
  __int64 *v9; // rbx
  __int128 v10; // xmm0
  __int64 v11; // rcx
  __int64 *v12; // rdi
  __int64 v13; // rdi
  __int128 v14; // xmm0
  __int64 *v15; // r14
  __int64 *v16; // rsi
  int v17; // eax
  unsigned __int8 *v18; // rcx
  int v19; // esi
  char *v20; // r12
  unsigned int v21; // esi
  unsigned int *v22; // r8
  unsigned int v23; // esi
  unsigned __int8 *v24; // r13
  bool v25; // zf
  unsigned int v26; // r14d
  char *v27; // r12
  char *v28; // r15
  int *v29; // rax
  int v30; // ecx
  __int64 i; // rax
  _BYTE *v32; // rax
  __int64 *v33; // rcx
  __int64 *j; // rax
  __int64 v35; // r8
  unsigned int v37; // [rsp+50h] [rbp-B0h]
  unsigned int v38; // [rsp+54h] [rbp-ACh] BYREF
  __int64 *v39; // [rsp+58h] [rbp-A8h] BYREF
  const char *v40; // [rsp+60h] [rbp-A0h] BYREF
  const char *v41; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v44; // [rsp+7Ch] [rbp-84h]
  unsigned int *v45; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v46; // [rsp+88h] [rbp-78h]
  const char *v47; // [rsp+90h] [rbp-70h] BYREF
  void *Source; // [rsp+98h] [rbp-68h]
  void *Destination; // [rsp+A0h] [rbp-60h]
  int *v50; // [rsp+A8h] [rbp-58h]
  _BYTE v51[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 **v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  unsigned __int8 **v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  int *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]

  v3 = this;
  *(_DWORD *)a3 = 2;
  v47 = (const char *)this;
  v4 = (unsigned __int8 *)(a3 + 16);
  v5 = (unsigned __int8 *)(a3 + 4);
  v38 = a2;
  *((_DWORD *)a3 + 1) = 4;
  v6 = 16;
  v7 = 0;
  *((_DWORD *)a3 + 2) = *((_DWORD *)v3 + 32);
  *((_DWORD *)a3 + 3) = *((_DWORD *)v3 + 36);
  v8 = (__int64 **)*((_QWORD *)v3 + 17);
  v46 = (unsigned __int8 *)(a3 + 4);
  v9 = *v8;
  while ( v9 != *((__int64 **)v3 + 17) )
  {
    v10 = *((_OWORD *)v9 + 3);
    v11 = (__int64)(v4 + 4);
    v41 = (const char *)(v4 + 4);
    *(_OWORD *)v4 = v10;
    *((_OWORD *)v4 + 1) = *((_OWORD *)v9 + 4);
    *((_OWORD *)v4 + 2) = *((_OWORD *)v9 + 5);
    *((_OWORD *)v4 + 3) = *((_OWORD *)v9 + 6);
    *((_QWORD *)v4 + 8) = v9[14];
    *(_DWORD *)v4 = 3;
    *((_DWORD *)v4 + 1) = 18;
    *((_DWORD *)v4 + 15) = *((unsigned __int8 *)v9 + 120);
    *((_DWORD *)v4 + 16) = *((unsigned __int8 *)v9 + 121);
    if ( *((_DWORD *)v4 + 17) != v9[17] )
    {
      *((_DWORD *)v3 + 14) = -2147467259;
      if ( (unsigned int)dword_180052170 > 2 )
      {
        LODWORD(v39) = *((_DWORD *)v3 + 14);
        LODWORD(v42) = *((_DWORD *)v9 + 34);
        v43 = *((_DWORD *)v4 + 17);
        v40 = "pModemStateHdr->numSIMSlot != sims.size()";
        v41 = "WwanController::BuildCellularStateSnapshot";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v11,
          (__int64)byte_180047ECB,
          (__int64)a3,
          0,
          (const unsigned __int16 **)&v40,
          (__int64)&v43,
          (__int64)&v42,
          (const unsigned __int16 **)&v41,
          (__int64)&v39);
      }
      return *((unsigned int *)v3 + 14);
    }
    v12 = (__int64 *)v9[16];
    v6 = (unsigned int)(v6 + 72);
    v40 = (const char *)v4;
    v4 += 72;
    v37 = v6;
    v13 = *v12;
    while ( v13 != v9[16] )
    {
      v14 = *(_OWORD *)(v13 + 44);
      v45 = (unsigned int *)(v4 + 4);
      *(_OWORD *)v4 = v14;
      *((_OWORD *)v4 + 1) = *(_OWORD *)(v13 + 60);
      *((_OWORD *)v4 + 2) = *(_OWORD *)(v13 + 76);
      *((_OWORD *)v4 + 3) = *(_OWORD *)(v13 + 92);
      *(_OWORD *)(v4 + 60) = *(_OWORD *)(v13 + 104);
      *(_DWORD *)v4 = 2;
      *((_DWORD *)v4 + 1) = 19;
      v15 = (__int64 *)*((_QWORD *)v3 + 19);
      v16 = (__int64 *)v15[1];
      if ( *((_BYTE *)v16 + 25) )
        goto LABEL_57;
      do
      {
        if ( memcmp_0(v16 + 4, (const void *)(v13 + 28), 0x10u) >= 0 )
        {
          v15 = v16;
          v16 = (__int64 *)*v16;
        }
        else
        {
          v16 = (__int64 *)v16[2];
        }
      }
      while ( !*((_BYTE *)v16 + 25) );
      v39 = v15;
      if ( v15 == *((__int64 **)v3 + 19) || (v17 = memcmp_0((const void *)(v13 + 28), v15 + 4, 0x10u), v7 = 0, v17 < 0) )
      {
LABEL_57:
        *((_DWORD *)v3 + 14) = -2147467259;
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v40 = (const char *)(v13 + 28);
          v47 = "the executor is not in the list";
          v41 = "WwanController::BuildCellularStateSnapshot";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
            v11,
            (__int64)&word_180047E3E,
            (__int64)a3,
            v7,
            (const unsigned __int16 **)&v47,
            (__int64 *)&v40,
            (const unsigned __int16 **)&v41);
        }
        return *((unsigned int *)v3 + 14);
      }
      v18 = v4;
      v6 = v37 + 76;
      v19 = *((_DWORD *)v15 + 58);
      v20 = (char *)(v15[26] + 20);
      v4 += 76;
      v42 = v18;
      v37 += 76;
      if ( v19 )
      {
        v21 = 4 * v19;
        memcpy_s(v4, v21, v20, v21);
        v22 = v45;
        v20 += v21;
        v4 += v21;
        v6 = v21 + v37;
        v37 += v21;
        *v45 += *((_DWORD *)v39 + 58);
        v11 = *v22;
        v7 = 0;
      }
      else
      {
        *((_DWORD *)v18 + 17) = 0;
        v11 = *v45;
      }
      v23 = 0;
      v44 = 0;
      if ( *((_DWORD *)v42 + 18) )
      {
        v24 = v42;
        do
        {
          *(_DWORD *)v4 = 1;
          Source = v20 + 100;
          v37 = v6 + 96;
          *((_DWORD *)v4 + 1) = 24;
          v25 = (v20[8] & 2) == 0;
          v50 = (int *)(v4 + 4);
          Destination = v4 + 96;
          if ( !v25 )
          {
            memcpy_s(v4 + 8, 0x20u, v20 + 12, 0x20u);
            *((_DWORD *)v4 + 10) = *((_DWORD *)v20 + 11);
          }
          if ( (v20[8] & 4) != 0 )
            memcpy_s(v4 + 44, 0x2Au, v20 + 48, 0x2Au);
          if ( (v20[8] & 8) != 0 )
            *((_DWORD *)v4 + 22) = *((_DWORD *)v20 + 23);
          if ( (v20[8] & 0x10) != 0 )
            *((_DWORD *)v4 + 23) = *((_DWORD *)v20 + 24);
          v26 = *((_DWORD *)v4 + 23) + *((_DWORD *)v4 + 22);
          if ( v26 )
          {
            if ( (unsigned int)dword_180052170 > 5 )
            {
              v43 = *((_DWORD *)v4 + 23);
              LODWORD(v42) = *((_DWORD *)v4 + 22);
              v57 = 4;
              LODWORD(v39) = v23 + 1;
              v56 = &v43;
              v54 = &v42;
              v52 = &v39;
              v55 = 4;
              v53 = 4;
              tlgWriteTransfer_EventWriteTransfer(&dword_180052170, byte_180048733, 0, 0, 5, v51);
            }
            v27 = (char *)Source;
            LogByteArray(v11, v26, Source, v7);
            v28 = (char *)Destination;
            memcpy_s(Destination, v26, v27, v26);
            v6 = v26 + v37;
            v20 = &v27[v26];
            v23 = v44;
            v37 += v26;
            v4 = (unsigned __int8 *)&v28[4 * ((v26 + 3) >> 2)];
            v29 = v50;
            *v50 += (v26 + 3) >> 2;
          }
          else
          {
            v20 = (char *)Source;
            v4 = (unsigned __int8 *)Destination;
            if ( (unsigned int)dword_180052170 > 5 )
            {
              v53 = 4;
              LODWORD(v39) = v23 + 1;
              v52 = &v39;
              tlgWriteTransfer_EventWriteTransfer(&dword_180052170, byte_1800487AB, 0, 0, 3, v51);
            }
            v29 = v50;
            v6 = v37;
          }
          ++v23;
          v30 = *v29;
          v44 = v23;
          v11 = *v45 + v30;
          *v45 = v11;
        }
        while ( v23 < *((_DWORD *)v24 + 18) );
        v3 = (WwanController *)v47;
        v7 = 0;
      }
      a3 = (char *)v40;
      *((_DWORD *)v40 + 1) += v11;
      if ( !*(_BYTE *)(v13 + 25) )
      {
        i = *(_QWORD *)(v13 + 16);
        if ( *(_BYTE *)(i + 25) )
        {
          for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 25) && v13 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v13 = i;
LABEL_44:
          v13 = i;
        }
        else
        {
          v11 = *(_QWORD *)i;
          if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
            goto LABEL_44;
          do
          {
            v13 = v11;
            v11 = *(_QWORD *)v11;
          }
          while ( !*(_BYTE *)(v11 + 25) );
        }
      }
    }
    v5 = v46;
    *(_DWORD *)v46 += *(_DWORD *)v41;
    if ( !*((_BYTE *)v9 + 25) )
    {
      v32 = (_BYTE *)v9[2];
      if ( v32[25] )
      {
        for ( j = (__int64 *)v9[1]; !*((_BYTE *)j + 25) && v9 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v9 = j;
        v9 = j;
      }
      else
      {
        v33 = *(__int64 **)v32;
        if ( *(_BYTE *)(*(_QWORD *)v32 + 25LL) )
        {
          v9 = (__int64 *)v9[2];
        }
        else
        {
          do
          {
            v9 = v33;
            v33 = (__int64 *)*v33;
          }
          while ( !*((_BYTE *)v33 + 25) );
        }
        v5 = v46;
      }
    }
  }
  v35 = v38;
  if ( (unsigned int)v6 <= v38 && *((_DWORD *)v3 + 48) == *(_DWORD *)v5 )
  {
    if ( (unsigned int)dword_180052170 > 5 )
    {
      v38 = *((_DWORD *)v3 + 48);
      v41 = "WwanController::BuildCellularStateSnapshot";
      v40 = "Cellular Snapshot built";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&unk_180048BA0,
        v35,
        0,
        (const unsigned __int16 **)&v40,
        (__int64)&v38,
        (const unsigned __int16 **)&v41);
    }
  }
  else
  {
    *((_DWORD *)v3 + 14) = -2147467259;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v38 = *((_DWORD *)v3 + 14);
      v40 = "cbUsed > cbCSS";
      LODWORD(v42) = v6;
      v41 = "WwanController::BuildCellularStateSnapshot";
      LODWORD(v39) = v35;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v5,
        (__int64)byte_180047C4D,
        v35,
        0,
        (const unsigned __int16 **)&v40,
        (__int64)&v42,
        (__int64)&v39,
        (const unsigned __int16 **)&v41,
        (__int64)&v38);
      v5 = v46;
    }
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v38 = *((_DWORD *)v3 + 14);
      LODWORD(v39) = *(_DWORD *)v5;
      LODWORD(v42) = *((_DWORD *)v3 + 48);
      v40 = "m_lenCSSinDWORD != pCellStateHdr->meta.lenTotal";
      v41 = "WwanController::BuildCellularStateSnapshot";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v5,
        (__int64)byte_18004880D,
        v35,
        v7,
        (const unsigned __int16 **)&v40,
        (__int64)&v42,
        (__int64)&v39,
        (const unsigned __int16 **)&v41,
        (__int64)&v38);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v6, v35, v7);
  }
  return *((unsigned int *)v3 + 14);
}

```

## disassembly

```asm
0x18000a59c  mov     [rsp-8+arg_8], rbx
0x18000a5a1  push    rbp
0x18000a5a2  push    rsi
0x18000a5a3  push    rdi
0x18000a5a4  push    r12
0x18000a5a6  push    r13
0x18000a5a8  push    r14
0x18000a5aa  push    r15
0x18000a5ac  lea     rbp, [rsp-10h]
0x18000a5b1  sub     rsp, 110h
0x18000a5b8  mov     rax, cs:__security_cookie
0x18000a5bf  xor     rax, rsp
0x18000a5c2  mov     [rbp+40h+var_40], rax
0x18000a5c6  mov     r13, rcx
0x18000a5c9  mov     dword ptr [r8], 2
0x18000a5d0  mov     [rbp+40h+var_B0], rcx
0x18000a5d4  lea     r15, [r8+10h]
0x18000a5d8  lea     rcx, [r8+4]
0x18000a5dc  mov     [rsp+140h+var_EC], edx
0x18000a5e0  mov     dword ptr [rcx], 4
0x18000a5e6  mov     edx, 10h
0x18000a5eb  mov     eax, [r13+80h]
0x18000a5f2  xor     r9d, r9d
0x18000a5f5  mov     [r8+8], eax
0x18000a5f9  mov     eax, [r13+90h]
0x18000a600  mov     [r8+0Ch], eax
0x18000a604  mov     rbx, [r13+88h]
0x18000a60b  mov     [rbp+40h+var_B8], rcx
0x18000a60f  mov     rbx, [rbx]
0x18000a612  cmp     rbx, [r13+88h]
0x18000a619  jz      loc_18000AB93
0x18000a61f  movups  xmm0, xmmword ptr [rbx+30h]
0x18000a623  lea     rcx, [r15+4]
0x18000a627  mov     [rsp+140h+var_D8], rcx
0x18000a62c  movups  xmmword ptr [r15], xmm0
0x18000a630  movups  xmm1, xmmword ptr [rbx+40h]
0x18000a634  movups  xmmword ptr [r15+10h], xmm1
0x18000a639  movups  xmm0, xmmword ptr [rbx+50h]
0x18000a63d  movups  xmmword ptr [r15+20h], xmm0
0x18000a642  movups  xmm1, xmmword ptr [rbx+60h]
0x18000a646  movups  xmmword ptr [r15+30h], xmm1
0x18000a64b  movsd   xmm0, qword ptr [rbx+70h]
0x18000a650  movsd   qword ptr [r15+40h], xmm0
0x18000a656  mov     dword ptr [r15], 3
0x18000a65d  mov     dword ptr [rcx], 12h
0x18000a663  movzx   eax, byte ptr [rbx+78h]
0x18000a667  mov     [r15+3Ch], eax
0x18000a66b  movzx   eax, byte ptr [rbx+79h]
0x18000a66f  mov     [r15+40h], eax
0x18000a673  mov     eax, [r15+44h]
0x18000a677  cmp     rax, [rbx+88h]
0x18000a67e  jnz     loc_18000AB07
0x18000a684  mov     rdi, [rbx+80h]
0x18000a68b  add     edx, 48h ; 'H'
0x18000a68e  mov     [rsp+140h+var_E0], r15
0x18000a693  add     r15, 48h ; 'H'
0x18000a697  mov     [rsp+140h+var_F0], edx
0x18000a69b  mov     rdi, [rdi]
0x18000a69e  cmp     rdi, [rbx+80h]
0x18000a6a5  jz      loc_18000AA3E
0x18000a6ab  movups  xmm0, xmmword ptr [rdi+2Ch]
0x18000a6af  lea     rax, [r15+4]
0x18000a6b3  mov     [rbp+40h+var_C0], rax
0x18000a6b7  lea     r12, [rdi+1Ch]
0x18000a6bb  movups  xmmword ptr [r15], xmm0
0x18000a6bf  movups  xmm1, xmmword ptr [rdi+3Ch]
0x18000a6c3  movups  xmmword ptr [r15+10h], xmm1
0x18000a6c8  movups  xmm0, xmmword ptr [rdi+4Ch]
0x18000a6cc  movups  xmmword ptr [r15+20h], xmm0
0x18000a6d1  movups  xmm1, xmmword ptr [rdi+5Ch]
0x18000a6d5  movups  xmmword ptr [r15+30h], xmm1
0x18000a6da  movups  xmm0, xmmword ptr [rdi+68h]
0x18000a6de  movups  xmmword ptr [r15+3Ch], xmm0
0x18000a6e3  mov     dword ptr [r15], 2
0x18000a6ea  mov     dword ptr [rax], 13h
0x18000a6f0  mov     rax, [r13+98h]
0x18000a6f7  mov     r14, rax
0x18000a6fa  mov     rsi, [rax+8]
0x18000a6fe  cmp     [rsi+19h], r9b
0x18000a702  jnz     loc_18000AAA6
0x18000a708  lea     rcx, [rsi+20h]; Buf1
0x18000a70c  mov     r8d, 10h; Size
0x18000a712  mov     rdx, r12; Buf2
0x18000a715  call    memcmp_0
0x18000a71a  test    eax, eax
0x18000a71c  jns     short loc_18000A724
0x18000a71e  mov     rsi, [rsi+10h]
0x18000a722  jmp     short loc_18000A72A
0x18000a724  mov     r14, rsi
0x18000a727  mov     rsi, [rsi]
0x18000a72a  cmp     byte ptr [rsi+19h], 0
0x18000a72e  jz      short loc_18000A708
0x18000a730  mov     [rsp+140h+var_E8], r14
0x18000a735  cmp     r14, [r13+98h]
0x18000a73c  jz      loc_18000AAA6
0x18000a742  lea     rdx, [r14+20h]; Buf2
0x18000a746  mov     r8d, 10h; Size
0x18000a74c  mov     rcx, r12; Buf1
0x18000a74f  call    memcmp_0
0x18000a754  xor     r9d, r9d
0x18000a757  test    eax, eax
0x18000a759  js      loc_18000AAA6
0x18000a75f  mov     edx, [rsp+140h+var_F0]
0x18000a763  mov     rcx, r15
0x18000a766  mov     r12, [r14+0D0h]
0x18000a76d  add     edx, 4Ch ; 'L'
0x18000a770  mov     esi, [r14+0E8h]
0x18000a777  add     r12, 14h
0x18000a77b  add     r15, 4Ch ; 'L'
0x18000a77f  mov     [rsp+140h+var_D0], rcx
0x18000a784  mov     [rsp+140h+var_F0], edx
0x18000a788  test    esi, esi
0x18000a78a  jz      short loc_18000A7CD
0x18000a78c  shl     esi, 2
0x18000a78f  mov     r8, r12; Source
0x18000a792  mov     r9d, esi; SourceSize
0x18000a795  mov     rcx, r15; Destination
0x18000a798  mov     edx, esi; DestinationSize
0x18000a79a  mov     r14d, esi
0x18000a79d  call    cs:__imp_memcpy_s
0x18000a7a3  mov     r8, [rbp+40h+var_C0]
0x18000a7a7  add     r12, r14
0x18000a7aa  mov     edx, [rsp+140h+var_F0]
0x18000a7ae  add     r15, r14
0x18000a7b1  mov     rax, [rsp+140h+var_E8]
0x18000a7b6  add     edx, esi
0x18000a7b8  mov     [rsp+140h+var_F0], edx
0x18000a7bc  mov     eax, [rax+0E8h]
0x18000a7c2  add     [r8], eax
0x18000a7c5  mov     ecx, [r8]
0x18000a7c8  xor     r9d, r9d
0x18000a7cb  jmp     short loc_18000A7D7
0x18000a7cd  mov     [rcx+44h], r9d
0x18000a7d1  mov     rcx, [rbp+40h+var_C0]
0x18000a7d5  mov     ecx, [rcx]
0x18000a7d7  mov     rax, [rsp+140h+var_D0]
0x18000a7dc  mov     esi, r9d
0x18000a7df  mov     [rsp+140h+var_C4], r9d
0x18000a7e4  cmp     [rax+48h], r9d
0x18000a7e8  jbe     loc_18000A9E3
0x18000a7ee  mov     r13, rax
0x18000a7f1  lea     rax, [r12+64h]
0x18000a7f6  mov     dword ptr [r15], 1
0x18000a7fd  mov     [rbp+40h+Source], rax
0x18000a801  add     edx, 60h ; '`'
0x18000a804  lea     rax, [r15+4]
0x18000a808  mov     [rsp+140h+var_F0], edx
0x18000a80c  mov     dword ptr [rax], 18h
0x18000a812  test    byte ptr [r12+8], 2
0x18000a818  mov     [rbp+40h+var_98], rax
0x18000a81c  lea     rax, [r15+60h]
0x18000a820  mov     [rbp+40h+Destination], rax
0x18000a824  jz      short loc_18000A848
0x18000a826  mov     eax, 20h ; ' '
0x18000a82b  lea     r8, [r12+0Ch]; Source
0x18000a830  mov     r9d, eax; SourceSize
0x18000a833  lea     rcx, [r15+8]; Destination
0x18000a837  mov     edx, eax; DestinationSize
0x18000a839  call    cs:__imp_memcpy_s
0x18000a83f  mov     eax, [r12+2Ch]
0x18000a844  mov     [r15+28h], eax
0x18000a848  mov     edx, 4
0x18000a84d  test    [r12+8], dl
0x18000a852  jz      short loc_18000A86B
0x18000a854  lea     eax, [rdx+26h]
0x18000a857  mov     r9d, eax; SourceSize
0x18000a85a  lea     r8, [r12+30h]; Source
0x18000a85f  mov     edx, eax; DestinationSize
0x18000a861  lea     rcx, [r15+2Ch]; Destination
0x18000a865  call    cs:__imp_memcpy_s
0x18000a86b  test    byte ptr [r12+8], 8
0x18000a871  jz      short loc_18000A87C
0x18000a873  mov     eax, [r12+5Ch]
0x18000a878  mov     [r15+58h], eax
0x18000a87c  test    byte ptr [r12+8], 10h
0x18000a882  jz      short loc_18000A88D
0x18000a884  mov     eax, [r12+60h]
0x18000a889  mov     [r15+5Ch], eax
0x18000a88d  mov     r14d, [r15+58h]
0x18000a891  mov     eax, cs:dword_180052170
0x18000a897  add     r14d, [r15+5Ch]
0x18000a89b  jz      loc_18000A969
0x18000a8a1  cmp     eax, 5
0x18000a8a4  jbe     short loc_18000A91A
0x18000a8a6  mov     eax, [r15+5Ch]
0x18000a8aa  lea     rdx, byte_180048733
0x18000a8b1  mov     [rsp+140h+var_C8], eax
0x18000a8b5  lea     rcx, dword_180052170
0x18000a8bc  mov     eax, [r15+58h]
0x18000a8c0  xor     r9d, r9d
0x18000a8c3  mov     dword ptr [rsp+140h+var_D0], eax
0x18000a8c7  xor     r8d, r8d
0x18000a8ca  lea     eax, [rsi+1]
0x18000a8cd  mov     [rbp+40h+var_48], 4
0x18000a8d5  mov     dword ptr [rsp+140h+var_E8], eax
0x18000a8d9  lea     rax, [rsp+140h+var_C8]
0x18000a8de  mov     [rbp+40h+var_50], rax
0x18000a8e2  lea     rax, [rsp+140h+var_D0]
0x18000a8e7  mov     [rbp+40h+var_60], rax
0x18000a8eb  lea     rax, [rsp+140h+var_E8]
0x18000a8f0  mov     [rbp+40h+var_70], rax
0x18000a8f4  lea     rax, [rbp+40h+var_90]
0x18000a8f8  mov     [rsp+140h+var_118], rax
0x18000a8fd  mov     dword ptr [rsp+140h+var_120], 5
0x18000a905  mov     [rbp+40h+var_58], 4
0x18000a90d  mov     [rbp+40h+var_68], 4
0x18000a915  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a91a  mov     r12, [rbp+40h+Source]
0x18000a91e  mov     edx, r14d
0x18000a921  mov     r8, r12
0x18000a924  call    _LogByteArray
0x18000a929  mov     r15, [rbp+40h+Destination]
0x18000a92d  mov     r8, r12; Source
0x18000a930  mov     rcx, r15; Destination
0x18000a933  mov     r9d, r14d; SourceSize
0x18000a936  mov     edx, r14d; DestinationSize
0x18000a939  mov     esi, r14d
0x18000a93c  call    cs:__imp_memcpy_s
0x18000a942  mov     edx, [rsp+140h+var_F0]
0x18000a946  lea     eax, [r14+3]
0x18000a94a  shr     eax, 2
0x18000a94d  add     edx, r14d
0x18000a950  mov     ecx, eax
0x18000a952  add     r12, rsi
0x18000a955  mov     esi, [rsp+140h+var_C4]
0x18000a959  mov     [rsp+140h+var_F0], edx
0x18000a95d  lea     r15, [r15+rax*4]
0x18000a961  mov     rax, [rbp+40h+var_98]
0x18000a965  add     [rax], ecx
0x18000a967  jmp     short loc_18000A9C0
0x18000a969  mov     r12, [rbp+40h+Source]
0x18000a96d  mov     r15, [rbp+40h+Destination]
0x18000a971  cmp     eax, 5
0x18000a974  jbe     short loc_18000A9B8
0x18000a976  lea     eax, [rsi+1]
0x18000a979  mov     [rbp+40h+var_68], 4
0x18000a981  mov     dword ptr [rsp+140h+var_E8], eax
0x18000a985  lea     rdx, byte_1800487AB
0x18000a98c  lea     rax, [rsp+140h+var_E8]
0x18000a991  xor     r9d, r9d
0x18000a994  mov     [rbp+40h+var_70], rax
0x18000a998  lea     rcx, dword_180052170
0x18000a99f  lea     rax, [rbp+40h+var_90]
0x18000a9a3  xor     r8d, r8d
0x18000a9a6  mov     [rsp+140h+var_118], rax
0x18000a9ab  mov     dword ptr [rsp+140h+var_120], 3
0x18000a9b3  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a9b8  mov     rax, [rbp+40h+var_98]
0x18000a9bc  mov     edx, [rsp+140h+var_F0]
0x18000a9c0  mov     r8, [rbp+40h+var_C0]
0x18000a9c4  inc     esi
0x18000a9c6  mov     ecx, [rax]
0x18000a9c8  mov     [rsp+140h+var_C4], esi
0x18000a9cc  add     ecx, [r8]
0x18000a9cf  mov     [r8], ecx
0x18000a9d2  cmp     esi, [r13+48h]
0x18000a9d6  jb      loc_18000A7F1
0x18000a9dc  mov     r13, [rbp+40h+var_B0]
0x18000a9e0  xor     r9d, r9d
0x18000a9e3  mov     r8, [rsp+140h+var_E0]
0x18000a9e8  add     [r8+4], ecx
0x18000a9ec  cmp     [rdi+19h], r9b
0x18000a9f0  jnz     loc_18000A69E
0x18000a9f6  mov     rax, [rdi+10h]
0x18000a9fa  cmp     [rax+19h], r9b
0x18000a9fe  jnz     short loc_18000AA1D
0x18000aa00  mov     rcx, [rax]
0x18000aa03  cmp     [rcx+19h], r9b
0x18000aa07  jnz     short loc_18000AA36
0x18000aa09  mov     rax, [rcx]
0x18000aa0c  mov     rdi, rcx
0x18000aa0f  mov     rcx, rax
0x18000aa12  cmp     [rax+19h], r9b
0x18000aa16  jz      short loc_18000AA09
0x18000aa18  jmp     loc_18000A69E
0x18000aa1d  mov     rax, [rdi+8]
0x18000aa21  jmp     short loc_18000AA30
0x18000aa23  cmp     rdi, [rax+10h]
0x18000aa27  jnz     short loc_18000AA36
0x18000aa29  mov     rdi, rax
0x18000aa2c  mov     rax, [rax+8]
0x18000aa30  cmp     [rax+19h], r9b
0x18000aa34  jz      short loc_18000AA23
0x18000aa36  mov     rdi, rax
0x18000aa39  jmp     loc_18000A69E
0x18000aa3e  mov     rax, [rsp+140h+var_D8]
0x18000aa43  mov     rcx, [rbp+40h+var_B8]
0x18000aa47  mov     eax, [rax]
0x18000aa49  add     [rcx], eax
0x18000aa4b  cmp     [rbx+19h], r9b
0x18000aa4f  jnz     loc_18000A612
0x18000aa55  mov     rax, [rbx+10h]
0x18000aa59  cmp     [rax+19h], r9b
0x18000aa5d  jnz     short loc_18000AA85
0x18000aa5f  mov     rcx, [rax]
0x18000aa62  cmp     [rcx+19h], r9b
0x18000aa66  jnz     short loc_18000AA79
0x18000aa68  mov     rax, [rcx]
0x18000aa6b  mov     rbx, rcx
0x18000aa6e  mov     rcx, rax
  ... truncated ...
```
