# SpQueryContextAttributes

- ea: `0x180002a80`
- end: `0x180003465`
- name: `SpQueryContextAttributes`
- size: `2533`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a80`
- `0x180004e60`
- `0x180006c50`
- `0x18002ed58`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180002b5c`
- `ntdll!RtlReleaseResource` at `0x180002b5c`
- `ntdll!RtlAcquireResourceShared` at `0x180002b20`
- `ntdll!RtlAcquireResourceShared` at `0x180002b20`

## string_xrefs

- `0x180002d25`: `NTLM Security Package`

## pseudocode

```c
__int64 __fastcall SpQueryContextAttributes(struct _LIST_ENTRY *a1, unsigned int a2, int *a3)
{
  _QWORD *v6; // rcx
  unsigned int v7; // ecx
  unsigned int v8; // ebx
  struct _RTL_RESOURCE *v9; // rbp
  struct _LIST_ENTRY near **v10; // rcx
  struct _LIST_ENTRY near *i; // rax
  struct _LIST_ENTRY near *v12; // rdi
  int *v13; // rbx
  int *v14; // r15
  unsigned int v15; // ebp
  __int64 v17; // rax
  __int64 v18; // rcx
  _OWORD *v19; // rcx
  struct _LIST_ENTRY *v20; // rax
  __int64 v21; // rbx
  void *v22; // rax
  size_t v23; // rbx
  _WORD *v24; // rax
  size_t Flink_low; // rbx
  void *v26; // rax
  unsigned int v27; // ebx
  unsigned int v28; // eax
  void *v29; // rax
  size_t v30; // rbx
  __int64 (__fastcall **v31)(__int64); // rax
  void *v32; // rax
  int v33; // ecx
  int v34; // eax
  const wchar_t *v35; // r15
  int v36; // eax
  __int64 (__fastcall **v37)(__int64, __int64); // rax
  __int64 v38; // rax
  __int64 v39; // rbx
  void *v41; // rax
  struct _LIST_ENTRY *Flink; // rax
  __int64 v43; // rbx
  void *v44; // rax
  __int64 v45; // rcx
  size_t v46; // rbx
  _WORD *v47; // rax
  struct _LIST_ENTRY *v48; // rax
  struct _LIST_ENTRY *v49; // rax
  struct _LIST_ENTRY *v50; // rdx
  int v51; // eax
  int v52; // ecx
  struct _LIST_ENTRY *Blink; // rax
  unsigned int v54; // r13d

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x200) != 0 )
      WPP_SF_q(v6[2], 10, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
  }
  v7 = ((unsigned int)a1 >> 4)
     + ((unsigned int)a1 >> 16)
     + ((unsigned int)a1 >> 24)
     + (_DWORD)a1
     + ((unsigned int)a1 >> 8);
  v8 = (unsigned __int8)(v7 + (v7 >> 4));
  v9 = (struct _RTL_RESOURCE *)&(&NtLmUserContextLock)[12 * (v8 & (NtLmUserContextLockCount - 1))];
  RtlAcquireResourceShared(v9, 1u);
  v10 = &(&NtLmUserContextList)[2 * v8];
  for ( i = *v10; ; i = i->Flink )
  {
    v12 = 0;
    if ( i == (struct _LIST_ENTRY near *)v10 )
      break;
    v12 = i;
    if ( i[2].Blink == a1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&i[10].Blink);
      break;
    }
  }
  v13 = 0;
  v14 = 0;
  RtlReleaseResource(v9);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1, v12);
  if ( v12 )
  {
    v15 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a2);
    if ( !a2 )
    {
      *a3 = 2888;
      a3[1] = ((__int64)v12[3].Flink & 0x8030) != 0 ? 0x10 : 0;
      if ( ((__int64)v12[3].Flink & 0x20) != 0 )
      {
        a3[2] = 1;
        a3[3] = 16;
      }
      else
      {
        a3[2] = 0;
        a3[3] = ((__int64)v12[3].Flink & 0x8010) != 0 ? 0x10 : 0;
      }
      goto LABEL_22;
    }
    switch ( a2 )
    {
      case 1u:
        Flink = v12[8].Flink;
        if ( !Flink )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
          }
          v47 = (_WORD *)(*(__int64 (__fastcall **)(__int64))UserFunctions)(2);
          *(_QWORD *)a3 = v47;
          *v47 = 0;
          goto LABEL_22;
        }
        v43 = -1;
        do
          ++v43;
        while ( *((_WORD *)&Flink->Flink + v43) );
        v44 = (void *)(*(__int64 (__fastcall **)(_QWORD))UserFunctions)((unsigned int)(2 * v43 + 2));
        *(_QWORD *)a3 = v44;
        if ( v44 )
        {
          v46 = 2LL * (unsigned int)v43;
          memcpy_0(v44, v12[8].Flink, v46);
          *(_WORD *)(v46 + *(_QWORD *)a3) = 0;
          goto LABEL_22;
        }
        v14 = a3;
        v15 = -1073741801;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
        goto LABEL_100;
      case 3u:
        v20 = v12[8].Flink;
        if ( v20 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_WORD *)&v20->Flink + v21) );
          v22 = (void *)(*(__int64 (__fastcall **)(_QWORD))UserFunctions)((unsigned int)(2 * v21 + 2));
          *((_QWORD *)a3 + 1) = v22;
          if ( !v22 )
          {
            v13 = a3;
            v15 = -1073741801;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
LABEL_141:
            if ( v13 )
            {
              v45 = *((_QWORD *)v13 + 1);
              if ( v45 )
                goto LABEL_102;
            }
            goto LABEL_21;
          }
          v23 = 2LL * (unsigned int)v21;
          memcpy_0(v22, v12[8].Flink, v23);
          *(_WORD *)(v23 + *((_QWORD *)a3 + 1)) = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
          }
          v24 = (_WORD *)(*(__int64 (__fastcall **)(__int64))UserFunctions)(2);
          *((_QWORD *)a3 + 1) = v24;
          *v24 = 0;
        }
        *a3 = 0;
        goto LABEL_22;
      case 5u:
        v33 = (int)v12[3].Flink;
        if ( (v33 & 0x20000000) != 0 )
        {
          a3[4] = 128;
        }
        else
        {
          v34 = 40;
          if ( v33 < 0 )
            v34 = 56;
          a3[4] = v34;
        }
        a3[6] = 26625;
        v35 = L"HMAC-MD5";
        if ( ((__int64)v12[3].Flink & 0x80000) == 0 )
          v35 = L"RSADSI RC4-CRC32";
        v36 = -138;
        if ( ((__int64)v12[3].Flink & 0x80000) == 0 )
          v36 = -132;
        a3[5] = v36;
        v37 = (__int64 (__fastcall **)(__int64, __int64))UserFunctions;
        *(_QWORD *)a3 = 0;
        *((_QWORD *)a3 + 1) = 0;
        v38 = (*v37)(22, 4294967164LL);
        *((_QWORD *)a3 + 1) = v38;
        if ( !v38 )
          goto LABEL_92;
        v39 = -1;
        *(_OWORD *)v38 = *(_OWORD *)L"RSADSI RC4";
        *(_QWORD *)(v38 + 14) = *(_QWORD *)L"RC4";
        while ( v35[++v39] != 0 )
          ;
        v41 = (void *)(*(__int64 (__fastcall **)(_QWORD))UserFunctions)((unsigned int)(2 * v39 + 2));
        *(_QWORD *)a3 = v41;
        if ( v41 )
        {
          memcpy_0(v41, v35, 2LL * (unsigned int)(v39 + 1));
        }
        else
        {
          v15 = -1073741670;
          (*(void (__fastcall **)(_QWORD))(UserFunctions + 8))(*((_QWORD *)a3 + 1));
          *((_QWORD *)a3 + 1) = 0;
        }
        goto LABEL_22;
      case 8u:
        v48 = v12[11].Flink;
        if ( !v48 )
          goto LABEL_113;
        *(_QWORD *)a3 = v48;
        goto LABEL_22;
      case 9u:
        v31 = (__int64 (__fastcall **)(__int64))UserFunctions;
        *a3 = 16;
        v32 = (void *)(*v31)(16);
        *((_QWORD *)a3 + 1) = v32;
        if ( !v32 )
          goto LABEL_92;
        memcpy_0(v32, (char *)&v12[9].Flink + 4, (unsigned int)*a3);
        goto LABEL_22;
      case 0xAu:
      case 0xCu:
        v17 = (*(__int64 (__fastcall **)(__int64))UserFunctions)(86);
        *(_QWORD *)a3 = v17;
        if ( !v17 )
        {
          v15 = -1073741670;
          goto LABEL_139;
        }
        *(_QWORD *)(v17 + 16) = v17 + 32;
        *(_QWORD *)(*(_QWORD *)a3 + 24LL) = *(_QWORD *)(*(_QWORD *)a3 + 16LL) + 10LL;
        v18 = *(_QWORD *)(*(_QWORD *)a3 + 16LL);
        *(_QWORD *)v18 = *(_QWORD *)L"NTLM";
        *(_WORD *)(v18 + 8) = pszPackageName[4];
        v19 = *(_OWORD **)(*(_QWORD *)a3 + 24LL);
        *v19 = *(_OWORD *)L"NTLM Security Package";
        v19[1] = *(_OWORD *)L"urity Package";
        *(_OWORD *)((char *)v19 + 28) = *(_OWORD *)L"Package";
        *(_WORD *)(*(_QWORD *)a3 + 4LL) = 1;
        *(_WORD *)(*(_QWORD *)a3 + 6LL) = 10;
        **(_DWORD **)a3 = 42478391;
        *(_DWORD *)(*(_QWORD *)a3 + 8LL) = 2888;
        if ( a2 == 12 )
          a3[2] = 0;
        goto LABEL_22;
      case 0xBu:
        *a3 = (int)v12[12].Flink;
        goto LABEL_22;
      case 0xEu:
        v50 = v12[11].Flink;
        v51 = 0;
        *a3 = 0;
        v52 = (int)v12[3].Flink;
        if ( (v52 & 0x20) != 0 )
          v51 = 16;
        if ( (v52 & 0x10) != 0 )
        {
          if ( v50 )
            v51 |= 0x2000Cu;
          else
            v51 |= 0x1000Cu;
        }
        if ( (v52 & 0x800) != 0 )
        {
          if ( v50 )
            v51 |= 0x100000u;
          else
            v51 |= 0x40000u;
        }
        if ( (v52 & 0x40) != 0 )
          v51 |= 0x400u;
        if ( (v52 & 0x100000) != 0 )
        {
          if ( v50 )
            v51 |= 0x80000u;
          else
            v51 |= 0x20000u;
        }
        if ( (v52 & 0x4000) != 0 )
          v51 |= 2u;
        *a3 = v51;
        goto LABEL_22;
      case 0x11u:
        if ( !a3 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
          v15 = -1073741811;
          goto LABEL_22;
        }
        *((_QWORD *)a3 + 1) = 0;
        if ( !v12[8].Blink )
        {
          *a3 = 0;
          goto LABEL_22;
        }
        Flink_low = LODWORD(v12[9].Flink);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
            (unsigned int)Flink_low);
        v26 = (void *)(*(__int64 (__fastcall **)(_QWORD))UserFunctions)((unsigned int)Flink_low);
        *((_QWORD *)a3 + 1) = v26;
        if ( v26 )
        {
          memcpy_0(v26, v12[8].Blink, Flink_low);
          *a3 = Flink_low;
          goto LABEL_22;
        }
        goto LABEL_92;
      case 0x12u:
        Blink = v12[3].Blink;
        if ( Blink )
          *(_QWORD *)a3 = Blink;
        else
          v15 = -2146893045;
        goto LABEL_22;
      case 0x15u:
        v49 = v12[11].Blink;
        if ( v49 )
          *(_QWORD *)a3 = v49;
        else
LABEL_113:
          v15 = -2146893054;
        goto LABEL_22;
      case 0x1Bu:
        if ( a3 )
        {
          if ( v12[16].Blink
            && ((v27 = 32766, v28 = LODWORD(v12[17].Flink) >> 1, v28 > 0x7FFE)
             || (v27 = LODWORD(v12[17].Flink) >> 1, v28)) )
          {
            v29 = (void *)(*(__int64 (__fastcall **)(_QWORD))UserFunctions)(2 * v27 + 2);
            *(_QWORD *)a3 = v29;
            if ( v29 )
            {
              v30 = 2LL * v27;
              memcpy_0(v29, v12[16].Blink, v30);
              *(_WORD *)(v30 + *(_QWORD *)a3) = 0;
            }
            else
            {
LABEL_92:
              v15 = -1073741670;
            }
          }
          else
          {
            v15 = -2146893053;
          }
        }
        else
        {
          v15 = -1073741811;
        }
        goto LABEL_22;
      case 0x25u:
        *a3 = (LODWORD(v12[3].Flink) >> 14) & 1;
        goto LABEL_22;
      default:
        v15 = -1073741637;
        goto LABEL_139;
    }
  }
  v15 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
LABEL_139:
  v54 = a2 - 1;
  if ( v54 )
  {
    if ( v54 != 2 )
      goto LABEL_21;
    goto LABEL_141;
  }
LABEL_100:
  if ( v14 )
  {
    v45 = *(_QWORD *)v14;
    if ( *(_QWORD *)v14 )
LABEL_102:
      NtLmFree(v45);
  }
LABEL_21:
  if ( !v12 )
  {
LABEL_30:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v15);
    return v15;
  }
LABEL_22:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v12);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v12[10].Blink, 0xFFFFFFFF) == 1 )
    FreeUserContext((struct _NTLM_CLIENT_CONTEXT *)v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
    goto LABEL_30;
  }
  return v15;
}

```

## disassembly

```asm
0x180002a80  push    rbx
0x180002a82  push    rbp
0x180002a83  push    rsi
0x180002a84  push    rdi
0x180002a85  push    r12
0x180002a87  push    r13
0x180002a89  push    r14
0x180002a8b  push    r15
0x180002a8d  sub     rsp, 38h
0x180002a91  mov     r14, r8
0x180002a94  mov     r13d, edx
0x180002a97  mov     rsi, rcx
0x180002a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002aa1  lea     r12, WPP_GLOBAL_Control
0x180002aa8  mov     eax, 0Ah
0x180002aad  cmp     rcx, r12
0x180002ab0  jz      short loc_180002AD1
0x180002ab2  test    dword ptr [rcx+1Ch], 100h
0x180002ab9  jnz     loc_180002E46
0x180002abf  cmp     rcx, r12
0x180002ac2  jz      short loc_180002AD1
0x180002ac4  test    dword ptr [rcx+1Ch], 200h
0x180002acb  jnz     loc_180002E6C
0x180002ad1  mov     edx, esi
0x180002ad3  lea     rdi, __ImageBase
0x180002ada  shr     edx, 18h
0x180002add  lea     rbp, rva ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A[rdi]; _RTL_RESOURCE near * NtLmUserContextLock ...
0x180002ae4  mov     eax, esi
0x180002ae6  mov     ecx, esi
0x180002ae8  shr     eax, 10h
0x180002aeb  add     edx, eax
0x180002aed  shr     ecx, 8
0x180002af0  add     ecx, esi
0x180002af2  mov     eax, esi
0x180002af4  shr     eax, 4
0x180002af7  add     ecx, edx
0x180002af9  add     ecx, eax
0x180002afb  mov     dl, 1; Wait
0x180002afd  mov     eax, ecx
0x180002aff  shr     eax, 4
0x180002b02  add     eax, ecx
0x180002b04  mov     ecx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x180002b0a  movzx   ebx, al
0x180002b0d  dec     ecx
0x180002b0f  and     rcx, rbx
0x180002b12  lea     rax, [rcx+rcx*2]
0x180002b16  shl     rax, 5
0x180002b1a  add     rbp, rax
0x180002b1d  mov     rcx, rbp; Resource
0x180002b20  call    cs:__imp_RtlAcquireResourceShared
0x180002b26  mov     eax, ebx
0x180002b28  lea     rcx, rva ?NtLmUserContextList@@3PAU_LIST_ENTRY@@A[rdi]; _LIST_ENTRY near * NtLmUserContextList ...
0x180002b2f  shl     rax, 4
0x180002b33  add     rcx, rax
0x180002b36  mov     rax, [rcx]
0x180002b39  xor     edi, edi
0x180002b3b  cmp     rax, rcx
0x180002b3e  jz      short loc_180002B54
0x180002b40  mov     rdi, rax
0x180002b43  cmp     [rax+28h], rsi
0x180002b47  jnz     loc_180002E3E
0x180002b4d  lock inc dword ptr [rax+0A8h]
0x180002b54  xor     ebx, ebx
0x180002b56  xor     r15d, r15d
0x180002b59  mov     rcx, rbp; Resource
0x180002b5c  call    cs:__imp_RtlReleaseResource
0x180002b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b69  cmp     rcx, r12
0x180002b6c  jz      short loc_180002B7B
0x180002b6e  test    dword ptr [rcx+1Ch], 200h
0x180002b75  jnz     loc_180002D9E
0x180002b7b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002b82  test    rdi, rdi
0x180002b85  jz      loc_180002C59
0x180002b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b92  xor     ebp, ebp
0x180002b94  cmp     rcx, r12
0x180002b97  jz      short loc_180002BA6
0x180002b99  test    dword ptr [rcx+1Ch], 200h
0x180002ba0  jnz     loc_180002E86
0x180002ba6  test    r13d, r13d
0x180002ba9  jnz     loc_180002CA2
0x180002baf  mov     dword ptr [r14], 0B48h
0x180002bb6  mov     eax, [rdi+30h]
0x180002bb9  and     eax, 8030h
0x180002bbe  neg     eax
0x180002bc0  sbb     eax, eax
0x180002bc2  and     eax, 10h
0x180002bc5  mov     [r14+4], eax
0x180002bc9  test    byte ptr [rdi+30h], 20h
0x180002bcd  jz      loc_1800033B0
0x180002bd3  mov     dword ptr [r14+8], 1
0x180002bdb  mov     dword ptr [r14+0Ch], 10h
0x180002be3  jmp     short loc_180002BEA
0x180002be5  test    rdi, rdi
0x180002be8  jz      short loc_180002C2D
0x180002bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bf1  cmp     rcx, r12
0x180002bf4  jz      short loc_180002C03
0x180002bf6  test    dword ptr [rcx+1Ch], 200h
0x180002bfd  jnz     loc_180002D81
0x180002c03  lock xadd [rdi+0A8h], esi
0x180002c0b  cmp     esi, 1
0x180002c0e  jz      loc_180002C95
0x180002c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c1b  cmp     rcx, r12
0x180002c1e  jz      short loc_180002C46
0x180002c20  test    dword ptr [rcx+1Ch], 200h
0x180002c27  jnz     loc_1800033CC
0x180002c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c34  cmp     rcx, r12
0x180002c37  jz      short loc_180002C46
0x180002c39  test    dword ptr [rcx+1Ch], 100h
0x180002c40  jnz     loc_1800033E6
0x180002c46  mov     eax, ebp
0x180002c48  add     rsp, 38h
0x180002c4c  pop     r15
0x180002c4e  pop     r14
0x180002c50  pop     r13
0x180002c52  pop     r12
0x180002c54  pop     rdi
0x180002c55  pop     rsi
0x180002c56  pop     rbp
0x180002c57  pop     rbx
0x180002c58  retn
0x180002c59  mov     ebp, 0C0000008h
0x180002c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c65  cmp     rcx, r12
0x180002c68  jz      loc_180003381
0x180002c6e  test    dword ptr [rcx+1Ch], 200h
0x180002c75  jz      loc_180003381
0x180002c7b  mov     rcx, [rcx+10h]
0x180002c7f  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002c86  mov     edx, 57h ; 'W'
0x180002c8b  call    WPP_SF_
0x180002c90  jmp     loc_180003381
0x180002c95  mov     rcx, rdi; struct _NTLM_CLIENT_CONTEXT *
0x180002c98  call    ?FreeUserContext@@YAJPEAU_NTLM_CLIENT_CONTEXT@@@Z; FreeUserContext(_NTLM_CLIENT_CONTEXT *)
0x180002c9d  jmp     loc_180002C14
0x180002ca2  lea     eax, [r13-1]; switch 37 cases
0x180002ca6  cmp     eax, 24h
0x180002ca9  ja      def_180002CC8; jumptable 0000000180002CC8 default case, cases 2,4,6,7,13,15,16,19,20,22-26,28-36
0x180002caf  lea     rdx, __ImageBase
0x180002cb6  movzx   eax, ds:(byte_180003440 - 180000000h)[rdx+rax]
0x180002cbe  mov     ecx, ds:(jpt_180002CC8 - 180000000h)[rdx+rax*4]
0x180002cc5  add     rcx, rdx
0x180002cc8  jmp     rcx; switch jump
0x180002cca  mov     rax, cs:UserFunctions; jumptable 0000000180002CC8 cases 10,12
0x180002cd1  mov     ecx, 56h ; 'V'
0x180002cd6  mov     rax, [rax]
0x180002cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cde  mov     [r14], rax
0x180002ce1  mov     rcx, rax
0x180002ce4  test    rax, rax
0x180002ce7  jz      loc_180003293
0x180002ced  add     rax, 20h ; ' '
0x180002cf1  mov     [rcx+10h], rax
0x180002cf5  mov     rcx, [r14]
0x180002cf8  mov     rax, [rcx+10h]
0x180002cfc  add     rax, 0Ah
0x180002d00  mov     [rcx+18h], rax
0x180002d04  mov     rax, [r14]
0x180002d07  movsd   xmm0, qword ptr cs:pszPackageName; "NTLM"
0x180002d0f  mov     rcx, [rax+10h]
0x180002d13  movsd   qword ptr [rcx], xmm0
0x180002d17  movzx   eax, word ptr cs:pszPackageName+8; ""
0x180002d1e  mov     [rcx+8], ax
0x180002d22  mov     rax, [r14]
0x180002d25  movups  xmm0, xmmword ptr cs:aNtlmSecurityPa; "NTLM Security Package"
0x180002d2c  mov     rcx, [rax+18h]
0x180002d30  movups  xmmword ptr [rcx], xmm0
0x180002d33  movups  xmm1, xmmword ptr cs:aNtlmSecurityPa+10h; "urity Package"
0x180002d3a  movups  xmmword ptr [rcx+10h], xmm1
0x180002d3e  movups  xmm0, xmmword ptr cs:aNtlmSecurityPa+1Ch; "Package"
0x180002d45  movups  xmmword ptr [rcx+1Ch], xmm0
0x180002d49  mov     rax, [r14]
0x180002d4c  mov     word ptr [rax+4], 1
0x180002d52  mov     rax, [r14]
0x180002d55  mov     word ptr [rax+6], 0Ah
0x180002d5b  mov     rax, [r14]
0x180002d5e  mov     dword ptr [rax], 2882B37h
0x180002d64  mov     rax, [r14]
0x180002d67  mov     dword ptr [rax+8], 0B48h
0x180002d6e  cmp     r13d, 0Ch
0x180002d72  jnz     loc_180002BEA
0x180002d78  mov     [r14+8], ebx
0x180002d7c  jmp     loc_180002BEA
0x180002d81  mov     rcx, [rcx+10h]
0x180002d85  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002d8c  mov     edx, 10h
0x180002d91  mov     r9, rdi
0x180002d94  call    WPP_SF_q
0x180002d99  jmp     loc_180002C03
0x180002d9e  mov     rcx, [rcx+10h]
0x180002da2  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002da9  mov     edx, 0Ch
0x180002dae  mov     [rsp+78h+var_58], rdi
0x180002db3  mov     r9, rsi
0x180002db6  call    WPP_SF_qq
0x180002dbb  jmp     loc_180002B7B
0x180002dc0  mov     rax, [rdi+80h]; jumptable 0000000180002CC8 case 3
0x180002dc7  test    rax, rax
0x180002dca  jz      loc_180002EC4
0x180002dd0  mov     rbx, rsi
0x180002dd3  inc     rbx
0x180002dd6  cmp     [rax+rbx*2], bp
0x180002dda  jnz     short loc_180002DD3
0x180002ddc  mov     rax, cs:UserFunctions
0x180002de3  lea     ecx, ds:2[rbx*2]
0x180002dea  mov     rax, [rax]
0x180002ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df2  mov     [r14+8], rax
0x180002df6  mov     rcx, rax; void *
0x180002df9  test    rax, rax
0x180002dfc  jnz     loc_180002EA3
0x180002e02  mov     rbx, r14
0x180002e05  mov     ebp, 0C0000017h
0x180002e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e11  cmp     rcx, r12
0x180002e14  jz      loc_180003395
0x180002e1a  test    byte ptr [rcx+1Ch], 1
0x180002e1e  jz      loc_180003395
0x180002e24  mov     rcx, [rcx+10h]
0x180002e28  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002e2f  mov     edx, 59h ; 'Y'
0x180002e34  call    WPP_SF_
0x180002e39  jmp     loc_180003395
0x180002e3e  mov     rax, [rax]
0x180002e41  jmp     loc_180002B39
0x180002e46  mov     rcx, [rcx+10h]
0x180002e4a  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002e51  mov     edx, 56h ; 'V'
0x180002e56  call    WPP_SF_
0x180002e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e62  mov     eax, 0Ah
0x180002e67  jmp     loc_180002ABF
0x180002e6c  mov     rcx, [rcx+10h]
0x180002e70  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002e77  mov     edx, eax
0x180002e79  mov     r9, rsi
0x180002e7c  call    WPP_SF_q
0x180002e81  jmp     loc_180002AD1
0x180002e86  mov     rcx, [rcx+10h]
0x180002e8a  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002e91  mov     edx, 58h ; 'X'
0x180002e96  mov     r9d, r13d
0x180002e99  call    WPP_SF_d
0x180002e9e  jmp     loc_180002BA6
0x180002ea3  mov     rdx, [rdi+80h]; Src
0x180002eaa  mov     eax, ebx
0x180002eac  lea     rbx, [rax+rax]
0x180002eb0  mov     r8, rbx; Size
0x180002eb3  call    memcpy_0
0x180002eb8  mov     rcx, [r14+8]
0x180002ebc  xor     eax, eax
0x180002ebe  mov     [rbx+rcx], ax
0x180002ec2  jmp     short loc_180002F0E
0x180002ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ecb  cmp     rcx, r12
0x180002ece  jz      short loc_180002EEE
0x180002ed0  test    dword ptr [rcx+1Ch], 200h
0x180002ed7  jz      short loc_180002EEE
0x180002ed9  mov     rcx, [rcx+10h]
0x180002edd  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002ee4  mov     edx, 5Ah ; 'Z'
0x180002ee9  call    WPP_SF_
0x180002eee  mov     rax, cs:UserFunctions
0x180002ef5  mov     ecx, 2
0x180002efa  mov     rax, [rax]
0x180002efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f02  mov     rcx, rax
0x180002f05  mov     [r14+8], rax
0x180002f09  xor     eax, eax
0x180002f0b  mov     [rcx], ax
0x180002f0e  mov     [r14], ebp
0x180002f11  jmp     loc_180002BEA
0x180002f16  test    r14, r14; jumptable 0000000180002CC8 case 17
0x180002f19  jnz     short loc_180002F4C
0x180002f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f22  cmp     rcx, r12
0x180002f25  jz      short loc_180002F42
0x180002f27  test    byte ptr [rcx+1Ch], 1
0x180002f2b  jz      short loc_180002F42
0x180002f2d  mov     rcx, [rcx+10h]
0x180002f31  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180002f38  mov     edx, 5Bh ; '['
0x180002f3d  call    WPP_SF_
0x180002f42  mov     ebp, 0C000000Dh
0x180002f47  jmp     loc_180002BEA
0x180002f4c  mov     [r14+8], rbx
0x180002f50  cmp     [rdi+88h], rbx
0x180002f57  jnz     short loc_180002F61
0x180002f59  mov     [r14], ebx
0x180002f5c  jmp     loc_180002BEA
0x180002f61  mov     ebx, [rdi+90h]
0x180002f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f6e  cmp     rcx, r12
0x180002f71  jz      short loc_180002F94
0x180002f73  test    dword ptr [rcx+1Ch], 200h
0x180002f7a  jz      short loc_180002F94
  ... truncated ...
```
