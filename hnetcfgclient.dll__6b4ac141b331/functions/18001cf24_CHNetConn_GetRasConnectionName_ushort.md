# CHNetConn::GetRasConnectionName(ushort * *)

- ea: `0x18001cf24`
- end: `0x18001d366`
- name: `?GetRasConnectionName@CHNetConn@@IEAAJPEAPEAG@Z`
- size: `1090`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c070`

## callees

- `0x180005698`
- `0x18000a45c`
- `0x18000a484`
- `0x18001be10`
- `0x18001cf24`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d29d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d29d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d348`
- `RASAPI32!DwEnumEntryDetails` at `0x18001d0a4`
- `RASAPI32!DwEnumEntryDetails` at `0x18001d0eb`
- `RASAPI32!DwEnumEntryDetails` at `0x18001d0a4`
- `RASAPI32!DwEnumEntryDetails` at `0x18001d0eb`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetRasConnectionName(CHNetConn *this, unsigned __int16 **a2)
{
  int GuidInternal; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  _DWORD *v9; // rdi
  signed int v10; // r14d
  _DWORD *v11; // rax
  signed int v12; // r14d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int i; // r14d
  __int64 v17; // rcx
  __int64 v18; // rax
  _DWORD *v19; // r15
  __int64 v20; // rax
  __int64 v21; // r12
  unsigned __int16 *v22; // rax
  PVOID *v23; // rcx
  LPVOID pv; // [rsp+20h] [rbp-10h] BYREF
  struct _GUID *v25; // [rsp+28h] [rbp-8h] BYREF
  SIZE_T cb; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v25 = 0;
  pv = 0;
  LODWORD(cb) = 0;
  v27 = 0;
  GuidInternal = CHNetConn::GetGuidInternal(this, &v25);
  v5 = GuidInternal;
  if ( GuidInternal < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 325;
LABEL_10:
      WPP_SF_d(v6[2], v7, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)GuidInternal);
LABEL_11:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  if ( GuidInternal )
  {
LABEL_75:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  GuidInternal = (*(__int64 (__fastcall **)(CHNetConn *, LPVOID *))(*(_QWORD *)this + 48LL))(this, &pv);
  v5 = GuidInternal;
  if ( GuidInternal >= 0 )
  {
    if ( GuidInternal )
      goto LABEL_75;
    LODWORD(cb) = 18360;
    v9 = CoTaskMemAlloc(0x47B8u);
    if ( v9 )
    {
      *v9 = 3672;
      v10 = DwEnumEntryDetails(pv, v9, &cb, &v27);
      if ( v10 == 603 )
      {
        CoTaskMemFree(v9);
        v11 = CoTaskMemAlloc((unsigned int)cb);
        v9 = v11;
        if ( v11 )
        {
          *v11 = 3672;
          v12 = DwEnumEntryDetails(pv, v11, &cb, &v27);
          if ( v12 )
          {
            CoTaskMemFree(v9);
            v9 = 0;
            v5 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 327;
LABEL_47:
              v15 = v5;
              goto LABEL_48;
            }
          }
        }
        else
        {
          v5 = -2147024882;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 328;
            v15 = 2147942414LL;
LABEL_48:
            WPP_SF_d(v13[2], v14, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v15);
          }
        }
      }
      else if ( v10 )
      {
        CoTaskMemFree(v9);
        v9 = 0;
        v5 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 329;
          goto LABEL_47;
        }
      }
    }
    else
    {
      v5 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          330,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          2147942414LL);
      }
    }
    CoTaskMemFree(pv);
    if ( !v5 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v27 )
          goto LABEL_68;
        v17 = 918LL * i;
        v18 = *(_QWORD *)&v9[v17 + 3] - *(_QWORD *)&v25->Data1;
        if ( !v18 )
          v18 = *(_QWORD *)&v9[v17 + 5] - *(_QWORD *)v25->Data4;
        if ( !v18 )
          break;
      }
      v19 = &v9[v17];
      v20 = -1;
      do
        ++v20;
      while ( *((_WORD *)v19 + v20 + 148) );
      v21 = (unsigned int)(v20 + 1);
      v22 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21);
      *a2 = v22;
      if ( v22 )
      {
        StringCchCopyW(v22, (unsigned int)v21, (const unsigned __int16 *)v19 + 148);
      }
      else
      {
        v5 = -2147024882;
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_69:
          if ( i == v27 )
          {
            v5 = -2147023728;
            if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 && *((_BYTE *)v23 + 25) >= 2u )
              WPP_SF_d(v23[2], 332, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147943568LL);
          }
          CoTaskMemFree(v9);
          goto LABEL_11;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          331,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          2147942414LL);
      }
LABEL_68:
      v23 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_69;
    }
    goto LABEL_75;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 326;
    goto LABEL_10;
  }
LABEL_12:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 333, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001cf24  mov     [rsp-28h+arg_0], rbx
0x18001cf29  mov     [rsp-28h+arg_8], rdi
0x18001cf2e  push    rbp
0x18001cf2f  push    r12
0x18001cf31  push    r13
0x18001cf33  push    r14
0x18001cf35  push    r15
0x18001cf37  mov     rbp, rsp
0x18001cf3a  sub     rsp, 30h
0x18001cf3e  mov     r13, rdx
0x18001cf41  mov     rdi, rcx
0x18001cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf4b  lea     r14, WPP_GLOBAL_Control
0x18001cf52  mov     r15b, 8
0x18001cf55  cmp     rcx, r14
0x18001cf58  jz      short loc_18001CF7B
0x18001cf5a  test    [rcx+1Ch], r15b
0x18001cf5e  jz      short loc_18001CF7B
0x18001cf60  cmp     byte ptr [rcx+19h], 6
0x18001cf64  jb      short loc_18001CF7B
0x18001cf66  mov     rcx, [rcx+10h]
0x18001cf6a  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cf71  mov     edx, 144h
0x18001cf76  call    WPP_SF_
0x18001cf7b  xor     r12d, r12d
0x18001cf7e  lea     rdx, [rbp+var_8]; struct _GUID **
0x18001cf82  mov     rcx, rdi; this
0x18001cf85  mov     [rbp+var_8], r12
0x18001cf89  mov     [rbp+pv], r12
0x18001cf8d  mov     dword ptr [rbp+cb], r12d
0x18001cf91  mov     [rbp+arg_18], r12d
0x18001cf95  call    ?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z; CHNetConn::GetGuidInternal(_GUID * *)
0x18001cf9a  mov     ebx, eax
0x18001cf9c  test    eax, eax
0x18001cf9e  jns     loc_18001D025
0x18001cfa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfab  cmp     rcx, r14
0x18001cfae  jz      short loc_18001CFDB
0x18001cfb0  test    [rcx+1Ch], r15b
0x18001cfb4  jz      short loc_18001CFDB
0x18001cfb6  cmp     byte ptr [rcx+19h], 2
0x18001cfba  jb      short loc_18001CFDB
0x18001cfbc  mov     edx, 145h
0x18001cfc1  mov     rcx, [rcx+10h]
0x18001cfc5  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cfcc  mov     r9d, eax
0x18001cfcf  call    WPP_SF_d
0x18001cfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfdb  lea     r14, WPP_GLOBAL_Control
0x18001cfe2  cmp     rcx, r14
0x18001cfe5  jz      short loc_18001D00B
0x18001cfe7  test    [rcx+1Ch], r15b
0x18001cfeb  jz      short loc_18001D00B
0x18001cfed  cmp     byte ptr [rcx+19h], 6
0x18001cff1  jb      short loc_18001D00B
0x18001cff3  mov     rcx, [rcx+10h]
0x18001cff7  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cffe  mov     edx, 14Dh
0x18001d003  mov     r9d, ebx
0x18001d006  call    WPP_SF_d
0x18001d00b  mov     rdi, [rsp+30h+arg_8]
0x18001d010  mov     eax, ebx
0x18001d012  mov     rbx, [rsp+30h+arg_0]
0x18001d017  add     rsp, 30h
0x18001d01b  pop     r15
0x18001d01d  pop     r14
0x18001d01f  pop     r13
0x18001d021  pop     r12
0x18001d023  pop     rbp
0x18001d024  retn
0x18001d025  jnz     loc_18001D353
0x18001d02b  mov     rax, [rdi]
0x18001d02e  lea     rdx, [rbp+pv]
0x18001d032  mov     rcx, rdi
0x18001d035  mov     rax, [rax+30h]
0x18001d039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d03e  mov     ebx, eax
0x18001d040  test    eax, eax
0x18001d042  jns     short loc_18001D06A
0x18001d044  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d04b  cmp     rcx, r14
0x18001d04e  jz      short loc_18001CFDB
0x18001d050  test    [rcx+1Ch], r15b
0x18001d054  jz      short loc_18001CFDB
0x18001d056  cmp     byte ptr [rcx+19h], 2
0x18001d05a  jb      loc_18001CFDB
0x18001d060  mov     edx, 146h
0x18001d065  jmp     loc_18001CFC1
0x18001d06a  jnz     loc_18001D353
0x18001d070  mov     ecx, 47B8h; cb
0x18001d075  mov     dword ptr [rbp+cb], ecx
0x18001d078  call    cs:__imp_CoTaskMemAlloc
0x18001d07e  mov     rdi, rax
0x18001d081  mov     eax, 8007000Eh
0x18001d086  test    rdi, rdi
0x18001d089  jz      loc_18001D1FB
0x18001d08f  mov     dword ptr [rdi], 0E58h
0x18001d095  lea     r9, [rbp+arg_18]
0x18001d099  mov     rcx, [rbp+pv]
0x18001d09d  lea     r8, [rbp+cb]
0x18001d0a1  mov     rdx, rdi
0x18001d0a4  call    cs:__imp_DwEnumEntryDetails
0x18001d0aa  mov     r14d, eax
0x18001d0ad  cmp     eax, 25Bh
0x18001d0b2  jnz     loc_18001D195
0x18001d0b8  mov     rcx, rdi; pv
0x18001d0bb  call    cs:__imp_CoTaskMemFree
0x18001d0c1  mov     ecx, dword ptr [rbp+cb]; cb
0x18001d0c4  call    cs:__imp_CoTaskMemAlloc
0x18001d0ca  mov     rdi, rax
0x18001d0cd  test    rax, rax
0x18001d0d0  jz      loc_18001D159
0x18001d0d6  mov     dword ptr [rax], 0E58h
0x18001d0dc  lea     r9, [rbp+arg_18]
0x18001d0e0  mov     rcx, [rbp+pv]
0x18001d0e4  lea     r8, [rbp+cb]
0x18001d0e8  mov     rdx, rax
0x18001d0eb  call    cs:__imp_DwEnumEntryDetails
0x18001d0f1  mov     r14d, eax
0x18001d0f4  test    eax, eax
0x18001d0f6  jz      loc_18001D22D
0x18001d0fc  mov     rcx, rdi; pv
0x18001d0ff  call    cs:__imp_CoTaskMemFree
0x18001d105  mov     rdi, r12
0x18001d108  test    r14d, r14d
0x18001d10b  jg      short loc_18001D112
0x18001d10d  mov     ebx, r14d
0x18001d110  jmp     short loc_18001D11C
0x18001d112  movzx   ebx, r14w
0x18001d116  or      ebx, 80070000h
0x18001d11c  test    ebx, ebx
0x18001d11e  jns     loc_18001D22D
0x18001d124  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d12b  lea     r14, WPP_GLOBAL_Control
0x18001d132  cmp     rcx, r14
0x18001d135  jz      loc_18001D234
0x18001d13b  test    [rcx+1Ch], r15b
0x18001d13f  jz      loc_18001D234
0x18001d145  cmp     byte ptr [rcx+19h], 2
0x18001d149  jb      loc_18001D234
0x18001d14f  mov     edx, 147h
0x18001d154  jmp     loc_18001D1E6
0x18001d159  mov     eax, 8007000Eh
0x18001d15e  mov     ebx, eax
0x18001d160  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d167  lea     r14, WPP_GLOBAL_Control
0x18001d16e  cmp     rcx, r14
0x18001d171  jz      loc_18001D234
0x18001d177  test    [rcx+1Ch], r15b
0x18001d17b  jz      loc_18001D234
0x18001d181  cmp     byte ptr [rcx+19h], 2
0x18001d185  jb      loc_18001D234
0x18001d18b  mov     edx, 148h
0x18001d190  mov     r9d, eax
0x18001d193  jmp     short loc_18001D1E9
0x18001d195  test    r14d, r14d
0x18001d198  jz      loc_18001D22D
0x18001d19e  mov     rcx, rdi; pv
0x18001d1a1  call    cs:__imp_CoTaskMemFree
0x18001d1a7  mov     rdi, r12
0x18001d1aa  test    r14d, r14d
0x18001d1ad  jg      short loc_18001D1B4
0x18001d1af  mov     ebx, r14d
0x18001d1b2  jmp     short loc_18001D1BE
0x18001d1b4  movzx   ebx, r14w
0x18001d1b8  or      ebx, 80070000h
0x18001d1be  test    ebx, ebx
0x18001d1c0  jns     short loc_18001D22D
0x18001d1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1c9  lea     r14, WPP_GLOBAL_Control
0x18001d1d0  cmp     rcx, r14
0x18001d1d3  jz      short loc_18001D234
0x18001d1d5  test    [rcx+1Ch], r15b
0x18001d1d9  jz      short loc_18001D234
0x18001d1db  cmp     byte ptr [rcx+19h], 2
0x18001d1df  jb      short loc_18001D234
0x18001d1e1  mov     edx, 149h
0x18001d1e6  mov     r9d, ebx
0x18001d1e9  mov     rcx, [rcx+10h]
0x18001d1ed  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d1f4  call    WPP_SF_d
0x18001d1f9  jmp     short loc_18001D234
0x18001d1fb  mov     ebx, eax
0x18001d1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d204  cmp     rcx, r14
0x18001d207  jz      short loc_18001D22D
0x18001d209  test    [rcx+1Ch], r15b
0x18001d20d  jz      short loc_18001D22D
0x18001d20f  cmp     byte ptr [rcx+19h], 2
0x18001d213  jb      short loc_18001D22D
0x18001d215  mov     rcx, [rcx+10h]
0x18001d219  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d220  mov     edx, 14Ah
0x18001d225  mov     r9d, eax
0x18001d228  call    WPP_SF_d
0x18001d22d  lea     r14, WPP_GLOBAL_Control
0x18001d234  mov     rcx, [rbp+pv]; pv
0x18001d238  call    cs:__imp_CoTaskMemFree
0x18001d23e  test    ebx, ebx
0x18001d240  jnz     loc_18001D35A
0x18001d246  mov     rdx, [rbp+var_8]
0x18001d24a  mov     r14d, r12d
0x18001d24d  cmp     r14d, [rbp+arg_18]
0x18001d251  jnb     loc_18001D303
0x18001d257  mov     eax, r14d
0x18001d25a  imul    rcx, rax, 0E58h
0x18001d261  mov     rax, [rcx+rdi+0Ch]
0x18001d266  sub     rax, [rdx]
0x18001d269  jnz     short loc_18001D274
0x18001d26b  mov     rax, [rcx+rdi+14h]
0x18001d270  sub     rax, [rdx+8]
0x18001d274  test    rax, rax
0x18001d277  jz      short loc_18001D27E
0x18001d279  inc     r14d
0x18001d27c  jmp     short loc_18001D24D
0x18001d27e  lea     r15, [rcx+rdi]
0x18001d282  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d286  inc     rax
0x18001d289  cmp     [r15+rax*2+128h], r12w
0x18001d292  jnz     short loc_18001D286
0x18001d294  inc     eax
0x18001d296  mov     r12d, eax
0x18001d299  lea     rcx, [rax+rax]; cb
0x18001d29d  call    cs:__imp_CoTaskMemAlloc
0x18001d2a3  mov     [r13+0], rax
0x18001d2a7  test    rax, rax
0x18001d2aa  jz      short loc_18001D2C3
0x18001d2ac  lea     r8, [r15+128h]; unsigned __int16 *
0x18001d2b3  mov     edx, r12d; unsigned __int64
0x18001d2b6  mov     rcx, rax; unsigned __int16 *
0x18001d2b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d2be  mov     r15b, 8
0x18001d2c1  jmp     short loc_18001D303
0x18001d2c3  mov     r9d, 8007000Eh
0x18001d2c9  mov     ebx, r9d
0x18001d2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2d3  lea     rax, WPP_GLOBAL_Control
0x18001d2da  mov     r15b, 8
0x18001d2dd  cmp     rcx, rax
0x18001d2e0  jz      short loc_18001D311
0x18001d2e2  test    [rcx+1Ch], r15b
0x18001d2e6  jz      short loc_18001D311
0x18001d2e8  cmp     byte ptr [rcx+19h], 2
0x18001d2ec  jb      short loc_18001D311
0x18001d2ee  mov     rcx, [rcx+10h]
0x18001d2f2  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d2f9  mov     edx, 14Bh
0x18001d2fe  call    WPP_SF_d
0x18001d303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d30a  lea     rax, WPP_GLOBAL_Control
0x18001d311  cmp     r14d, [rbp+arg_18]
0x18001d315  jnz     short loc_18001D345
0x18001d317  mov     ebx, 80070490h
0x18001d31c  cmp     rcx, rax
0x18001d31f  jz      short loc_18001D345
0x18001d321  test    [rcx+1Ch], r15b
0x18001d325  jz      short loc_18001D345
0x18001d327  cmp     byte ptr [rcx+19h], 2
0x18001d32b  jb      short loc_18001D345
0x18001d32d  mov     rcx, [rcx+10h]
0x18001d331  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d338  mov     edx, 14Ch
0x18001d33d  mov     r9d, ebx
0x18001d340  call    WPP_SF_d
0x18001d345  mov     rcx, rdi; pv
0x18001d348  call    cs:__imp_CoTaskMemFree
0x18001d34e  jmp     loc_18001CFD4
0x18001d353  lea     r14, WPP_GLOBAL_Control
0x18001d35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d361  jmp     loc_18001CFE2
```
