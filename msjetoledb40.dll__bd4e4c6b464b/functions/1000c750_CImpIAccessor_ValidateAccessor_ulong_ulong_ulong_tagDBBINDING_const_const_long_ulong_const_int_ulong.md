# CImpIAccessor::ValidateAccessor(ulong,ulong,ulong,tagDBBINDING const * const,long *,ulong * const,int *,ulong)

- ea: `0x1000c750`
- end: `0x1000cc1e`
- name: `?ValidateAccessor@CImpIAccessor@@AAGJKKKQBUtagDBBINDING@@PAJQAKPAHK@Z`
- size: `1230`
- prototype: `int __stdcall(CImpIAccessor *__hidden this, unsigned int, unsigned int, unsigned int, const struct tagDBBINDING *const, int *, unsigned int *const, int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1000bea0`
- `0x1000c0d0`

## callees

- `0x1000ba90`
- `0x1000c750`
- `0x1001c6d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000cc03`
- `KERNEL32!LeaveCriticalSection` at `0x1000cc03`
- `KERNEL32!EnterCriticalSection` at `0x1000c793`
- `KERNEL32!EnterCriticalSection` at `0x1000c793`

## pseudocode

```c
int __userpurge CImpIAccessor::ValidateAccessor@<eax>(
        unsigned int a1@<edx>,
        int a2@<ecx>,
        CImpIAccessor *this,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        const struct tagDBBINDING *const a7,
        int *a8,
        unsigned int *const a9,
        int *a10,
        unsigned int a11)
{
  const struct tagDBBINDING *v11; // esi
  int v12; // edi
  int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // edx
  int v20; // edi
  int v21; // eax
  int *v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // edx
  GUID *v26; // edi
  __int128 v27; // xmm0
  bool v28; // cf
  bool v29; // zf
  GUID *v30; // edx
  __int128 *v31; // edi
  GUID *v32; // edx
  __int128 *v33; // edi
  __int128 v35; // [esp+10h] [ebp-44h] BYREF
  struct _RTL_CRITICAL_SECTION *v36; // [esp+20h] [ebp-34h]
  unsigned int v37; // [esp+24h] [ebp-30h]
  int v38; // [esp+28h] [ebp-2Ch]
  int v39; // [esp+2Ch] [ebp-28h]
  unsigned int v40; // [esp+30h] [ebp-24h]
  int v41; // [esp+34h] [ebp-20h]
  __int128 *v42; // [esp+38h] [ebp-1Ch]
  int v43; // [esp+3Ch] [ebp-18h]
  unsigned int v44; // [esp+40h] [ebp-14h]
  int v45; // [esp+44h] [ebp-10h]
  int v46; // [esp+50h] [ebp-4h]

  v40 = a1;
  v41 = a2;
  v11 = a7;
  v12 = 0;
  v45 = 0;
  v36 = &g_CriticalSection;
  EnterCriticalSection(&g_CriticalSection);
  v46 = 0;
  *a8 = 0;
  v13 = *(_DWORD *)(*(_DWORD *)(v41 + 8) + 96);
  v39 = v13;
  if ( v40 != 3 )
  {
    if ( v40 < 2 )
      goto LABEL_92;
    goto LABEL_5;
  }
  if ( (v13 & 0x100) == 0 )
  {
LABEL_5:
    v14 = 0;
    v44 = 0;
    if ( !a4 )
      goto LABEL_92;
    v15 = a5;
    v38 = 128;
    while ( 1 )
    {
      v43 = 52 * v14;
      v16 = *(_DWORD *)(52 * v14 + v15);
      v42 = *(__int128 **)(*(_DWORD *)(v41 + 8) + 148);
      if ( v16 > *((_DWORD *)v42 + 1) )
        goto LABEL_14;
      v17 = v43;
      v11 = a7;
      if ( *(_DWORD *)(v43 + a5 + 32) )
      {
        if ( a7 )
          *(&a7->iOrdinal + v14) = 3;
        goto LABEL_11;
      }
      if ( !v16 )
      {
        if ( (v39 & 8) != 0 )
        {
          v18 = *(unsigned __int16 *)(v43 + a5 + 48);
          if ( v18 == 3 || (_WORD)v18 == (_WORD)v38 )
            goto LABEL_24;
          if ( !(*(int (__thiscall **)(_DWORD, LPVOID, int, int))(*(_DWORD *)g_pIDataConvert + 16))(
                  *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 16),
                  g_pIDataConvert,
                  v18,
                  3) )
          {
            v14 = v44;
            v12 = v45;
            v17 = v43;
LABEL_24:
            v15 = a5;
            if ( (*(_BYTE *)(v17 + a5 + 28) & 1) != 0 && *(_DWORD *)(52 * v14 + a5 + 40) < 4u )
            {
              if ( a7 )
                *(&a7->iOrdinal + v14) = 3;
              v12 = -2147217887;
              v45 = -2147217887;
            }
            else
            {
              *a8 = 1;
            }
            goto LABEL_91;
          }
LABEL_20:
          if ( v11 )
            *(&v11->iOrdinal + v44) = 2;
          v14 = v44;
          v12 = -2147217887;
          v45 = -2147217887;
          goto LABEL_90;
        }
LABEL_14:
        if ( v11 )
          *(&v11->iOrdinal + v14) = 1;
LABEL_16:
        v12 = -2147217887;
        v45 = -2147217887;
        goto LABEL_90;
      }
      v19 = *(unsigned __int16 *)(v43 + a5 + 48);
      if ( (v19 & 0x1000) != 0 )
      {
        if ( !a7 )
          goto LABEL_11;
        v12 = -2147217887;
        *(&a7->iOrdinal + v14) = 3;
        v45 = -2147217887;
        goto LABEL_90;
      }
      if ( (v19 & 0x2000) != 0 && (v19 & 0xFFF) != 0x80 )
      {
        if ( a7 )
        {
          v12 = -2147217887;
          *(&a7->iOrdinal + v14) = 3;
          v45 = -2147217887;
          goto LABEL_90;
        }
LABEL_11:
        v12 = -2147217887;
        v45 = -2147217887;
LABEL_90:
        v15 = a5;
        goto LABEL_91;
      }
      if ( *((_DWORD *)v42 + 3) )
      {
        v12 = v45;
        v42 = (__int128 *)(*((_DWORD *)v42 + 3) - 104 + 104 * *(_DWORD *)(v43 + a5));
      }
      else
      {
        v42 = 0;
      }
      v11 = a7;
      if ( (*(_BYTE *)(52 * v14 + a5 + 28) & 1) != 0 )
        break;
LABEL_59:
      v15 = a5;
      v11 = a7;
      if ( *(_WORD *)(52 * v14 + a5 + 48) == 13 )
      {
        v23 = *((_DWORD *)v42 + 9);
        if ( v23 != 11 && v23 != 12 )
        {
          if ( a7 )
            *(&a7->iOrdinal + v14) = 5;
          v12 = -2147217887;
          v45 = -2147217887;
          goto LABEL_91;
        }
        v24 = *(_DWORD *)(52 * v14 + a5 + 20);
        if ( v24 )
        {
          v25 = *(_DWORD *)v24;
          v26 = &IID_ILockBytes;
          v27 = *(_OWORD *)(v24 + 4);
          v37 = *(_DWORD *)v24;
          v35 = v27;
          v42 = &v35;
          v40 = 12;
          do
          {
            v11 = a7;
            if ( v26->Data1 != *(_DWORD *)v42 )
            {
              v30 = &IID_ISequentialStream;
              v40 = 12;
              v31 = &v35;
              while ( v30->Data1 == *(_DWORD *)v31 )
              {
                v30 = (GUID *)((char *)v30 + 4);
                v31 = (__int128 *)((char *)v31 + 4);
                v28 = v40 < 4;
                v40 -= 4;
                if ( v28 )
                {
LABEL_85:
                  if ( v37 < 2 )
                    goto LABEL_89;
                  v29 = v37 == 4096;
                  goto LABEL_74;
                }
              }
              v32 = &IID_IUnknown;
              v40 = 12;
              v33 = &v35;
              while ( v32->Data1 == *(_DWORD *)v33 )
              {
                v32 = (GUID *)((char *)v32 + 4);
                v33 = (__int128 *)((char *)v33 + 4);
                v28 = v40 < 4;
                v40 -= 4;
                if ( v28 )
                  goto LABEL_85;
              }
              if ( a7 )
              {
                v12 = -2147217887;
                *(&a7->iOrdinal + v14) = 5;
                v45 = -2147217887;
                goto LABEL_90;
              }
              goto LABEL_77;
            }
            v42 = (__int128 *)((char *)v42 + 4);
            v26 = (GUID *)((char *)v26 + 4);
            v28 = v40 < 4;
            v40 -= 4;
          }
          while ( !v28 );
          if ( v25 <= 2 )
          {
            if ( v25 != 2 && v25 )
            {
              v29 = v25 == 1;
              goto LABEL_74;
            }
            goto LABEL_89;
          }
          v29 = v25 == 4096;
LABEL_74:
          if ( !v29 )
          {
            if ( a7 )
              *(&a7->iOrdinal + v14) = 4;
LABEL_77:
            v12 = -2147217887;
            v45 = -2147217887;
            goto LABEL_90;
          }
LABEL_89:
          v12 = v45;
          goto LABEL_90;
        }
      }
LABEL_91:
      v44 = ++v14;
      if ( v14 >= a4 )
        goto LABEL_92;
    }
    if ( !v42 )
    {
      if ( a7 )
      {
        v12 = -2147217887;
        *(&a7->iOrdinal + v14) = 1;
        v45 = -2147217887;
        goto LABEL_90;
      }
      goto LABEL_16;
    }
    v20 = *((unsigned __int16 *)v42 + 20);
    v37 = *((_DWORD *)v42 + 13);
    v43 = v20;
    v12 = v45;
    if ( (_WORD)v19 == 130 )
    {
      v40 = 2;
    }
    else
    {
      if ( (_WORD)v19 != 129 )
      {
LABEL_51:
        if ( (_WORD)v19 == 13 )
        {
          v22 = a8;
        }
        else
        {
          if ( (*(int (__thiscall **)(_DWORD, LPVOID, int, int))(*(_DWORD *)g_pIDataConvert + 16))(
                 *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 16),
                 g_pIDataConvert,
                 v43,
                 v19)
            && (*(int (__thiscall **)(_DWORD, LPVOID, _DWORD, int))(*(_DWORD *)g_pIDataConvert + 16))(
                 *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 16),
                 g_pIDataConvert,
                 *(unsigned __int16 *)(52 * v44 + a5 + 48),
                 v43) )
          {
            goto LABEL_20;
          }
          v21 = (*(int (__thiscall **)(_DWORD, LPVOID, _DWORD, int))(*(_DWORD *)g_pIDataConvert + 16))(
                  *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 16),
                  g_pIDataConvert,
                  *(unsigned __int16 *)(52 * v44 + a5 + 48),
                  v43);
          v14 = v44;
          v29 = v21 == 0;
          v12 = v45;
          v22 = a8;
          if ( !v29 )
            *a8 = 1;
        }
        if ( (v37 & 8) != 0 )
          *v22 = 1;
        goto LABEL_59;
      }
      v40 = 1;
    }
    v11 = a7;
    v12 = v45;
    if ( v40 > *(_DWORD *)(52 * v14 + a5 + 40) )
    {
      if ( a7 )
      {
        v12 = -2147217887;
        *(&a7->iOrdinal + v14) = 3;
        v45 = -2147217887;
        goto LABEL_90;
      }
      goto LABEL_11;
    }
    goto LABEL_51;
  }
  v12 = -2147217850;
LABEL_92:
  LeaveCriticalSection(&g_CriticalSection);
  return v12;
}

```

## disassembly

```asm
0x1000c750  mov     edi, edi
0x1000c752  push    ebp
0x1000c753  mov     ebp, esp
0x1000c755  push    0FFFFFFFFh
0x1000c757  push    offset ?ValidateAccessor@CImpIAccessor@@AAGJKKKQBUtagDBBINDING@@PAJQAKPAHK@Z_SEH
0x1000c75c  mov     eax, large fs:0
0x1000c762  push    eax
0x1000c763  sub     esp, 3Ch
0x1000c766  push    esi
0x1000c767  push    edi
0x1000c768  mov     eax, ___security_cookie
0x1000c76d  xor     eax, ebp
0x1000c76f  push    eax
0x1000c770  lea     eax, [ebp+var_C]
0x1000c773  mov     large fs:0, eax
0x1000c779  mov     [ebp+var_24], edx
0x1000c77c  mov     [ebp+var_20], ecx
0x1000c77f  mov     esi, [ebp+arg_10]
0x1000c782  xor     edi, edi
0x1000c784  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000c789  mov     [ebp+var_10], edi
0x1000c78c  mov     [ebp+var_34], offset ?g_CriticalSection@@3VCriticalSection@@A; CriticalSection g_CriticalSection
0x1000c793  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000c799  mov     eax, [ebp+arg_14]
0x1000c79c  mov     [ebp+var_4], edi
0x1000c79f  mov     [eax], edi
0x1000c7a1  mov     eax, [ebp+var_20]
0x1000c7a4  mov     eax, [eax+8]
0x1000c7a7  mov     ecx, [eax+60h]
0x1000c7aa  mov     eax, [ebp+var_24]
0x1000c7ad  mov     [ebp+var_28], ecx
0x1000c7b0  cmp     eax, 3
0x1000c7b3  jnz     short loc_1000C7C7
0x1000c7b5  test    ecx, 100h
0x1000c7bb  jz      short loc_1000C7D0
0x1000c7bd  mov     edi, 80040E46h
0x1000c7c2  jmp     loc_1000CBFE
0x1000c7c7  cmp     eax, 2
0x1000c7ca  jb      loc_1000CBFE
0x1000c7d0  xor     ecx, ecx
0x1000c7d2  mov     [ebp+var_14], ecx
0x1000c7d5  cmp     [ebp+arg_4], ecx
0x1000c7d8  jbe     loc_1000CBFE
0x1000c7de  mov     edx, [ebp+arg_8]
0x1000c7e1  mov     [ebp+var_2C], 80h
0x1000c7e8  nop     dword ptr [eax+eax+00000000h]
0x1000c7f0  imul    eax, ecx, 34h ; '4'
0x1000c7f3  mov     [ebp+var_18], eax
0x1000c7f6  mov     edx, [eax+edx]
0x1000c7f9  mov     eax, [ebp+var_20]
0x1000c7fc  mov     eax, [eax+8]
0x1000c7ff  mov     eax, [eax+94h]
0x1000c805  mov     [ebp+var_1C], eax
0x1000c808  cmp     edx, [eax+4]
0x1000c80b  ja      short loc_1000C843
0x1000c80d  mov     esi, [ebp+arg_8]
0x1000c810  mov     eax, [ebp+var_18]
0x1000c813  cmp     dword ptr [eax+esi+20h], 0
0x1000c818  mov     esi, [ebp+arg_10]
0x1000c81b  jz      short loc_1000C835
0x1000c81d  test    esi, esi
0x1000c81f  jz      short loc_1000C828
0x1000c821  mov     dword ptr [esi+ecx*4], 3
0x1000c828  mov     edi, 80040E21h
0x1000c82d  mov     [ebp+var_10], edi
0x1000c830  jmp     loc_1000CBEE
0x1000c835  test    edx, edx
0x1000c837  jnz     loc_1000C8EC
0x1000c83d  test    byte ptr [ebp+var_28], 8
0x1000c841  jnz     short loc_1000C85B
0x1000c843  test    esi, esi
0x1000c845  jz      short loc_1000C84E
0x1000c847  mov     dword ptr [esi+ecx*4], 1
0x1000c84e  mov     edi, 80040E21h
0x1000c853  mov     [ebp+var_10], edi
0x1000c856  jmp     loc_1000CBEE
0x1000c85b  mov     edx, [ebp+arg_8]
0x1000c85e  movzx   edx, word ptr [eax+edx+30h]
0x1000c863  cmp     edx, 3
0x1000c866  jz      short loc_1000C8B2
0x1000c868  cmp     dx, word ptr [ebp+var_2C]
0x1000c86c  jz      short loc_1000C8B2
0x1000c86e  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x1000c874  push    3
0x1000c876  push    edx
0x1000c877  push    ecx
0x1000c878  mov     eax, [ecx]
0x1000c87a  mov     edi, [eax+10h]
0x1000c87d  mov     ecx, edi
0x1000c87f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000c885  call    edi
0x1000c887  test    eax, eax
0x1000c889  jz      short loc_1000C8A9
0x1000c88b  test    esi, esi
0x1000c88d  jz      short loc_1000C899
0x1000c88f  mov     eax, [ebp+var_14]
0x1000c892  mov     dword ptr [esi+eax*4], 2
0x1000c899  mov     ecx, [ebp+var_14]
0x1000c89c  mov     edi, 80040E21h
0x1000c8a1  mov     [ebp+var_10], edi
0x1000c8a4  jmp     loc_1000CBEE
0x1000c8a9  mov     ecx, [ebp+var_14]
0x1000c8ac  mov     edi, [ebp+var_10]
0x1000c8af  mov     eax, [ebp+var_18]
0x1000c8b2  mov     edx, [ebp+arg_8]
0x1000c8b5  test    byte ptr [eax+edx+1Ch], 1
0x1000c8ba  jz      short loc_1000C8DE
0x1000c8bc  imul    eax, ecx, 34h ; '4'
0x1000c8bf  cmp     dword ptr [eax+edx+28h], 4
0x1000c8c4  jnb     short loc_1000C8DE
0x1000c8c6  test    esi, esi
0x1000c8c8  jz      short loc_1000C8D1
0x1000c8ca  mov     dword ptr [esi+ecx*4], 3
0x1000c8d1  mov     edi, 80040E21h
0x1000c8d6  mov     [ebp+var_10], edi
0x1000c8d9  jmp     loc_1000CBF1
0x1000c8de  mov     eax, [ebp+arg_14]
0x1000c8e1  mov     dword ptr [eax], 1
0x1000c8e7  jmp     loc_1000CBF1
0x1000c8ec  mov     edx, [ebp+arg_8]
0x1000c8ef  movzx   edx, word ptr [eax+edx+30h]
0x1000c8f4  test    edx, 1000h
0x1000c8fa  jz      short loc_1000C918
0x1000c8fc  test    esi, esi
0x1000c8fe  jz      loc_1000C828
0x1000c904  mov     edi, 80040E21h
0x1000c909  mov     dword ptr [esi+ecx*4], 3
0x1000c910  mov     [ebp+var_10], edi
0x1000c913  jmp     loc_1000CBEE
0x1000c918  test    edx, 2000h
0x1000c91e  jz      short loc_1000C94A
0x1000c920  mov     eax, edx
0x1000c922  and     eax, 0FFFh
0x1000c927  cmp     eax, 80h
0x1000c92c  jz      short loc_1000C94A
0x1000c92e  test    esi, esi
0x1000c930  jz      loc_1000C828
0x1000c936  mov     edi, 80040E21h
0x1000c93b  mov     dword ptr [esi+ecx*4], 3
0x1000c942  mov     [ebp+var_10], edi
0x1000c945  jmp     loc_1000CBEE
0x1000c94a  mov     eax, [ebp+var_1C]
0x1000c94d  mov     eax, [eax+0Ch]
0x1000c950  test    eax, eax
0x1000c952  jnz     short loc_1000C959
0x1000c954  mov     [ebp+var_1C], eax
0x1000c957  jmp     short loc_1000C974
0x1000c959  mov     esi, [ebp+var_18]
0x1000c95c  mov     edi, [ebp+arg_8]
0x1000c95f  imul    eax, [esi+edi], 68h ; 'h'
0x1000c963  mov     edi, [ebp+var_1C]
0x1000c966  mov     esi, [edi+0Ch]
0x1000c969  mov     edi, [ebp+var_10]
0x1000c96c  add     esi, 0FFFFFF98h
0x1000c96f  add     eax, esi
0x1000c971  mov     [ebp+var_1C], eax
0x1000c974  mov     esi, [ebp+arg_8]
0x1000c977  imul    eax, ecx, 34h ; '4'
0x1000c97a  test    byte ptr [eax+esi+1Ch], 1
0x1000c97f  mov     esi, [ebp+arg_10]
0x1000c982  jz      loc_1000CAB4
0x1000c988  mov     eax, [ebp+var_1C]
0x1000c98b  test    eax, eax
0x1000c98d  jnz     short loc_1000C9AB
0x1000c98f  test    esi, esi
0x1000c991  jz      loc_1000C84E
0x1000c997  mov     edi, 80040E21h
0x1000c99c  mov     dword ptr [esi+ecx*4], 1
0x1000c9a3  mov     [ebp+var_10], edi
0x1000c9a6  jmp     loc_1000CBEE
0x1000c9ab  movzx   edi, word ptr [eax+28h]
0x1000c9af  mov     eax, [eax+34h]
0x1000c9b2  mov     [ebp+var_30], eax
0x1000c9b5  mov     eax, 82h
0x1000c9ba  mov     [ebp+var_18], edi
0x1000c9bd  mov     edi, [ebp+var_10]
0x1000c9c0  cmp     ax, dx
0x1000c9c3  jz      short loc_1000C9D8
0x1000c9c5  mov     eax, 81h
0x1000c9ca  cmp     ax, dx
0x1000c9cd  jnz     short loc_1000CA10
0x1000c9cf  mov     [ebp+var_24], 1
0x1000c9d6  jmp     short loc_1000C9DF
0x1000c9d8  mov     [ebp+var_24], 2
0x1000c9df  mov     edi, [ebp+arg_8]
0x1000c9e2  mov     esi, [ebp+var_24]
0x1000c9e5  imul    eax, ecx, 34h ; '4'
0x1000c9e8  cmp     esi, [eax+edi+28h]
0x1000c9ec  mov     esi, [ebp+arg_10]
0x1000c9ef  mov     edi, [ebp+var_10]
0x1000c9f2  jbe     short loc_1000CA10
0x1000c9f4  test    esi, esi
0x1000c9f6  jz      loc_1000C828
0x1000c9fc  mov     edi, 80040E21h
0x1000ca01  mov     dword ptr [esi+ecx*4], 3
0x1000ca08  mov     [ebp+var_10], edi
0x1000ca0b  jmp     loc_1000CBEE
0x1000ca10  mov     eax, 0Dh
0x1000ca15  cmp     ax, dx
0x1000ca18  jz      loc_1000CAA5
0x1000ca1e  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x1000ca24  push    edx
0x1000ca25  push    [ebp+var_18]
0x1000ca28  mov     eax, [ecx]
0x1000ca2a  push    ecx
0x1000ca2b  mov     edi, [eax+10h]
0x1000ca2e  mov     ecx, edi
0x1000ca30  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000ca36  call    edi
0x1000ca38  test    eax, eax
0x1000ca3a  jz      short loc_1000CA6A
0x1000ca3c  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x1000ca42  mov     edx, [ebp+arg_8]
0x1000ca45  push    [ebp+var_18]
0x1000ca48  mov     eax, [ecx]
0x1000ca4a  mov     edi, [eax+10h]
0x1000ca4d  imul    eax, [ebp+var_14], 34h ; '4'
0x1000ca51  movzx   eax, word ptr [eax+edx+30h]
0x1000ca56  push    eax
0x1000ca57  push    ecx
0x1000ca58  mov     ecx, edi
0x1000ca5a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000ca60  call    edi
0x1000ca62  test    eax, eax
0x1000ca64  jnz     loc_1000C88B
0x1000ca6a  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x1000ca70  mov     edx, [ebp+arg_8]
0x1000ca73  push    [ebp+var_18]
0x1000ca76  mov     eax, [ecx]
0x1000ca78  mov     edi, [eax+10h]
0x1000ca7b  imul    eax, [ebp+var_14], 34h ; '4'
0x1000ca7f  movzx   eax, word ptr [eax+edx+30h]
0x1000ca84  push    eax
0x1000ca85  push    ecx
0x1000ca86  mov     ecx, edi
0x1000ca88  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000ca8e  call    edi
0x1000ca90  mov     ecx, [ebp+var_14]
0x1000ca93  test    eax, eax
0x1000ca95  mov     edi, [ebp+var_10]
0x1000ca98  mov     eax, [ebp+arg_14]
0x1000ca9b  jz      short loc_1000CAA8
0x1000ca9d  mov     dword ptr [eax], 1
0x1000caa3  jmp     short loc_1000CAA8
0x1000caa5  mov     eax, [ebp+arg_14]
0x1000caa8  test    byte ptr [ebp+var_30], 8
0x1000caac  jz      short loc_1000CAB4
0x1000caae  mov     dword ptr [eax], 1
0x1000cab4  mov     edx, [ebp+arg_8]
0x1000cab7  mov     esi, 0Dh
0x1000cabc  imul    eax, ecx, 34h ; '4'
0x1000cabf  cmp     si, [eax+edx+30h]
0x1000cac4  mov     esi, [ebp+arg_10]
0x1000cac7  jnz     loc_1000CBF1
0x1000cacd  mov     eax, [ebp+var_1C]
0x1000cad0  mov     eax, [eax+24h]
0x1000cad3  cmp     eax, 0Bh
0x1000cad6  jz      short loc_1000CAF5
0x1000cad8  cmp     eax, 0Ch
0x1000cadb  jz      short loc_1000CAF5
0x1000cadd  test    esi, esi
0x1000cadf  jz      short loc_1000CAE8
0x1000cae1  mov     dword ptr [esi+ecx*4], 5
0x1000cae8  mov     edi, 80040E21h
0x1000caed  mov     [ebp+var_10], edi
0x1000caf0  jmp     loc_1000CBF1
0x1000caf5  imul    eax, ecx, 34h ; '4'
0x1000caf8  mov     eax, [eax+edx+14h]
0x1000cafc  test    eax, eax
0x1000cafe  jz      loc_1000CBF1
0x1000cb04  mov     edx, [eax]
0x1000cb06  mov     edi, offset _IID_ILockBytes
0x1000cb0b  movups  xmm0, xmmword ptr [eax+4]
0x1000cb0f  lea     eax, [ebp+var_44]
0x1000cb12  mov     [ebp+var_30], edx
0x1000cb15  mov     [ebp+var_48], edx
0x1000cb18  movups  [ebp+var_44], xmm0
0x1000cb1c  mov     [ebp+var_1C], eax
0x1000cb1f  mov     [ebp+var_24], 0Ch
0x1000cb26  mov     esi, [ebp+var_1C]
0x1000cb29  mov     eax, [edi]
0x1000cb2b  cmp     eax, [esi]
0x1000cb2d  mov     esi, [ebp+arg_10]
0x1000cb30  jnz     short loc_1000CB79
0x1000cb32  add     [ebp+var_1C], 4
0x1000cb36  add     edi, 4
0x1000cb39  sub     [ebp+var_24], 4
0x1000cb3d  jnb     short loc_1000CB26
0x1000cb3f  cmp     edx, 2
0x1000cb42  ja      short loc_1000CB58
0x1000cb44  jz      loc_1000CBEB
0x1000cb4a  sub     edx, 0
0x1000cb4d  jz      loc_1000CBEB
0x1000cb53  sub     edx, 1
0x1000cb56  jmp     short loc_1000CB5E
0x1000cb58  cmp     edx, 1000h
0x1000cb5e  jz      loc_1000CBEB
0x1000cb64  test    esi, esi
0x1000cb66  jz      short loc_1000CB6F
0x1000cb68  mov     dword ptr [esi+ecx*4], 4
  ... truncated ...
```
