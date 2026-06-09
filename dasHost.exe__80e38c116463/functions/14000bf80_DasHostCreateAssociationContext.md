# DasHostCreateAssociationContext

- ea: `0x14000bf80`
- end: `0x14000c341`
- name: `DasHostCreateAssociationContext`
- size: `961`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned __int16 *, unsigned int, void *, HANDLE ExistingTokenHandle, unsigned int, __int64, struct _ASSOCIATION_ENTRY **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x140009090`
- `0x1400093e4`
- `0x14000afa4`
- `0x14000bc74`
- `0x14000bf80`
- `0x14001a83c`
- `0x14001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000bfea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000bfea`

## pseudocode

```c
__int64 __fastcall DasHostCreateAssociationContext(
        __int64 a1,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        void *a5,
        HANDLE ExistingTokenHandle,
        unsigned int a7,
        __int64 a8,
        struct _ASSOCIATION_ENTRY **a9)
{
  struct _ASSOCIATION_ENTRY *v10; // rsi
  __int64 v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int16 *v14; // rax
  signed int v15; // ebx
  unsigned __int64 v16; // r14
  int v17; // ecx
  unsigned __int64 v18; // r13
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rdi
  int v21; // r14d
  unsigned __int16 *v22; // r8
  unsigned int v23; // edx
  unsigned int v24; // r13d
  void *v25; // r10
  __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  __int64 v30; // rax
  unsigned __int16 *v31; // rsi
  unsigned __int16 *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rbp
  void *v35; // rax
  int v37; // [rsp+28h] [rbp-60h]
  void *v38; // [rsp+40h] [rbp-48h]
  struct _ASSOCIATION_ENTRY *v40; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v41; // [rsp+A8h] [rbp+20h]

  v41 = a4;
  v10 = 0;
  v40 = 0;
  v38 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      19,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EventActivityIdControl(2u, a2);
  if ( a3 )
  {
    v14 = a3;
    v12 = 768;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v12;
    }
    while ( v12 );
    v13 = (768 - v12) & -(__int64)(v12 != 0);
    v15 = v12 == 0 ? 0x80070057 : 0;
    if ( v12 )
    {
      v16 = 0;
      v15 = -2147024809;
      v17 = 0;
      if ( v13 )
      {
        LODWORD(v12) = 35;
        while ( 1 )
        {
          v18 = v16++;
          if ( a3[v17] == 35 )
            break;
          if ( (unsigned int)++v17 >= v13 )
            goto LABEL_51;
        }
        v19 = (unsigned __int16 *)DAF_user_alloc(2 * v16);
        v20 = v19;
        if ( !v19 )
        {
          v15 = -2147024882;
          goto LABEL_51;
        }
        v15 = StringCchCopyNW(v19, v16, a3, v18);
        if ( v15 )
          goto LABEL_50;
        v21 = a8;
        v22 = 0;
        v23 = 0;
        v24 = a7;
        if ( a7 )
        {
          while ( *(_DWORD *)(a8 + 40LL * v23 + 16) != 8
               || DEVPKEY_DasParam_PerUserSid != *(_OWORD *)(a8 + 40LL * v23)
               || !*(_QWORD *)(a8 + 40LL * v23 + 32)
               || !*(_DWORD *)(a8 + 40LL * v23 + 24)
               || *(_DWORD *)(a8 + 40LL * v23 + 20) != 18 )
          {
            if ( ++v23 >= a7 )
              goto LABEL_25;
          }
          v22 = *(unsigned __int16 **)(a8 + 40LL * v23 + 32);
        }
LABEL_25:
        v15 = CreateAssociationEntry(a2, v41, v20, 0, v22, a5, ExistingTokenHandle, &v40);
        if ( v15 )
          goto LABEL_45;
        v25 = 0;
        v38 = 0;
        v26 = 768;
        v27 = a3;
        do
        {
          if ( !*v27 )
            break;
          ++v27;
          --v26;
        }
        while ( v26 );
        v15 = v26 == 0 ? 0x80070057 : 0;
        v28 = (768 - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64);
        if ( v26 )
        {
          if ( v28 < 3 || (v29 = v28 - 1, v30 = 1, v29 <= 1) )
          {
LABEL_34:
            v15 = -2147024809;
          }
          else
          {
            while ( a3[v30] != 35 )
            {
              if ( ++v30 >= v29 )
                goto LABEL_34;
            }
            v31 = &a3[v30 + 1];
            if ( !v31 )
            {
              v15 = -2147024809;
              goto LABEL_45;
            }
            v32 = &a3[v30 + 1];
            v33 = 512;
            do
            {
              if ( !*v32 )
                break;
              ++v32;
              --v33;
            }
            while ( v33 );
            v15 = v33 == 0 ? 0x80070057 : 0;
            if ( !v33 )
              goto LABEL_45;
            v34 = -(__int64)(v33 != 0) & (2 * (512 - v33));
            v35 = DAF_user_alloc(v34 + 2);
            v38 = v35;
            if ( !v35 )
            {
              v15 = -2147024882;
              goto LABEL_45;
            }
            memcpy_0(v35, v31, v34 + 2);
            v25 = v38;
          }
        }
        if ( !v15 )
        {
          v10 = v40;
          v37 = v21;
          v15 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, unsigned int))(**((_QWORD **)v40 + 6) + 24LL))(
                  *((_QWORD *)v40 + 6),
                  v25,
                  v41,
                  *((_QWORD *)v40 + 7),
                  v24);
          if ( v15 >= 0 )
            *a9 = v10;
          goto LABEL_50;
        }
LABEL_45:
        v10 = v40;
LABEL_50:
        MIDL_user_free(v20);
      }
    }
  }
  else
  {
    v15 = -2147024809;
  }
LABEL_51:
  if ( v38 )
    MIDL_user_free(v38);
  if ( v15 < 0 && v10 )
    RemoveAssociationEntry(v10, v12, v13);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v12,
      v13,
      20,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v37,
      v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000bf80  mov     r11, rsp
0x14000bf83  mov     [r11+8], rbx
0x14000bf87  mov     [r11+20h], r9d
0x14000bf8b  mov     [r11+10h], rdx
0x14000bf8f  push    rbp
0x14000bf90  push    rsi
0x14000bf91  push    rdi
0x14000bf92  push    r12
0x14000bf94  push    r13
0x14000bf96  push    r14
0x14000bf98  push    r15
0x14000bf9a  sub     rsp, 50h
0x14000bf9e  xor     r13d, r13d
0x14000bfa1  mov     r15, r8
0x14000bfa4  mov     esi, r13d
0x14000bfa7  mov     [r11+18h], r13
0x14000bfab  mov     [rsp+88h+var_48], r13
0x14000bfb0  mov     rbx, rdx
0x14000bfb3  lea     rax, WPP_RECORDER_INITIALIZED
0x14000bfba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000bfc1  lea     rcx, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000bfc8  jz      short loc_14000BFE2
0x14000bfca  mov     [r11-68h], rcx
0x14000bfce  lea     r9d, [r13+13h]; int
0x14000bfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfd9  mov     rcx, [rcx+28h]; int
0x14000bfdd  call    WPP_RECORDER_SF_s
0x14000bfe2  mov     rdx, rbx; ActivityId
0x14000bfe5  mov     ecx, 2; ControlCode
0x14000bfea  call    cs:__imp_EventActivityIdControl
0x14000bff0  mov     rdi, r13
0x14000bff3  test    r15, r15
0x14000bff6  jz      loc_14000C2BC
0x14000bffc  mov     r12d, 300h
0x14000c002  mov     rax, r15
0x14000c005  mov     edx, r12d
0x14000c008  cmp     [rax], r13w
0x14000c00c  jz      short loc_14000C018
0x14000c00e  add     rax, 2
0x14000c012  sub     rdx, 1
0x14000c016  jnz     short loc_14000C008
0x14000c018  mov     rcx, r12
0x14000c01b  mov     rax, rdx
0x14000c01e  sub     rcx, rdx
0x14000c021  mov     ebp, 80070057h
0x14000c026  neg     rax
0x14000c029  mov     rax, rdx
0x14000c02c  sbb     r8, r8
0x14000c02f  and     r8, rcx
0x14000c032  neg     rax
0x14000c035  sbb     ebx, ebx
0x14000c037  not     ebx
0x14000c039  and     ebx, ebp
0x14000c03b  test    rdx, rdx
0x14000c03e  jz      loc_14000C2C1
0x14000c044  mov     r14, r13
0x14000c047  mov     ebx, ebp
0x14000c049  mov     ecx, r13d
0x14000c04c  test    r8, r8
0x14000c04f  jz      loc_14000C2C1
0x14000c055  mov     edx, 23h ; '#'
0x14000c05a  mov     eax, ecx
0x14000c05c  mov     r13, r14
0x14000c05f  inc     r14
0x14000c062  cmp     dx, [r15+rax*2]
0x14000c067  jz      short loc_14000C077
0x14000c069  inc     ecx
0x14000c06b  mov     eax, ecx
0x14000c06d  cmp     rax, r8
0x14000c070  jb      short loc_14000C05A
0x14000c072  jmp     loc_14000C2C1
0x14000c077  lea     rcx, [r14+r14]
0x14000c07b  call    DAF_user_alloc
0x14000c080  mov     rdi, rax
0x14000c083  test    rax, rax
0x14000c086  jnz     short loc_14000C092
0x14000c088  mov     ebx, 8007000Eh
0x14000c08d  jmp     loc_14000C2C1
0x14000c092  mov     r9, r13; unsigned __int64
0x14000c095  mov     r8, r15; unsigned __int16 *
0x14000c098  mov     rdx, r14; unsigned __int64
0x14000c09b  mov     rcx, rdi; unsigned __int16 *
0x14000c09e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000c0a3  xor     r13d, r13d
0x14000c0a6  mov     ebx, eax
0x14000c0a8  test    eax, eax
0x14000c0aa  jz      short loc_14000C0BC
0x14000c0ac  mov     rcx, rdi; void *
0x14000c0af  call    MIDL_user_free
0x14000c0b4  mov     edi, r13d
0x14000c0b7  jmp     loc_14000C2C1
0x14000c0bc  mov     r14, [rsp+88h+arg_38]
0x14000c0c4  mov     r8, r13
0x14000c0c7  mov     edx, r13d
0x14000c0ca  xor     r11d, r11d
0x14000c0cd  mov     r13d, [rsp+88h+arg_30]
0x14000c0d5  test    r13d, r13d
0x14000c0d8  jz      short loc_14000C128
0x14000c0da  mov     r9, qword ptr cs:DEVPKEY_DasParam_PerUserSid+8
0x14000c0e1  mov     r10, qword ptr cs:DEVPKEY_DasParam_PerUserSid
0x14000c0e8  mov     eax, edx
0x14000c0ea  lea     rcx, [rax+rax*4]
0x14000c0ee  cmp     dword ptr [r14+rcx*8+10h], 8
0x14000c0f4  jnz     short loc_14000C11C
0x14000c0f6  cmp     r10, [r14+rcx*8]
0x14000c0fa  jnz     short loc_14000C11C
0x14000c0fc  cmp     r9, [r14+rcx*8+8]
0x14000c101  jnz     short loc_14000C11C
0x14000c103  mov     rax, [r14+rcx*8+20h]
0x14000c108  test    rax, rax
0x14000c10b  jz      short loc_14000C11C
0x14000c10d  cmp     [r14+rcx*8+18h], r11d
0x14000c112  jz      short loc_14000C11C
0x14000c114  cmp     dword ptr [r14+rcx*8+14h], 12h
0x14000c11a  jz      short loc_14000C125
0x14000c11c  inc     edx
0x14000c11e  cmp     edx, r13d
0x14000c121  jb      short loc_14000C0E8
0x14000c123  jmp     short loc_14000C128
0x14000c125  mov     r8, rax
0x14000c128  mov     edx, [rsp+88h+arg_18]; unsigned int
0x14000c12f  lea     rax, [rsp+88h+arg_10]
0x14000c137  mov     rcx, [rsp+88h+arg_8]; struct _GUID *
0x14000c13f  xor     r9d, r9d; struct _GUID *
0x14000c142  mov     [rsp+88h+var_50], rax; struct _ASSOCIATION_ENTRY **
0x14000c147  mov     rax, [rsp+88h+arg_28]
0x14000c14f  mov     [rsp+88h+ExistingTokenHandle], rax; ExistingTokenHandle
0x14000c154  mov     rax, [rsp+88h+arg_20]
0x14000c15c  mov     [rsp+88h+var_60], rax; void *
0x14000c161  mov     [rsp+88h+MessageGuid], r8; unsigned __int16 *
0x14000c166  mov     r8, rdi; unsigned __int16 *
0x14000c169  call    ?CreateAssociationEntry@@YAJPEBU_GUID@@KPEBG01PEAX2PEAPEAU_ASSOCIATION_ENTRY@@@Z; CreateAssociationEntry(_GUID const *,ulong,ushort const *,_GUID const *,ushort const *,void *,void *,_ASSOCIATION_ENTRY * *)
0x14000c16e  xor     r8d, r8d
0x14000c171  mov     ebx, eax
0x14000c173  test    eax, eax
0x14000c175  jnz     loc_14000C295
0x14000c17b  mov     r10d, r8d
0x14000c17e  mov     [rsp+88h+var_48], r8
0x14000c183  mov     rcx, r12
0x14000c186  lea     r9d, [rbx+1]
0x14000c18a  mov     rax, r15
0x14000c18d  cmp     [rax], r8w
0x14000c191  jz      short loc_14000C19C
0x14000c193  add     rax, 2
0x14000c197  sub     rcx, r9
0x14000c19a  jnz     short loc_14000C18D
0x14000c19c  mov     rax, rcx
0x14000c19f  neg     rax
0x14000c1a2  mov     rax, rcx
0x14000c1a5  sbb     ebx, ebx
0x14000c1a7  sub     r12, rcx
0x14000c1aa  not     ebx
0x14000c1ac  and     ebx, ebp
0x14000c1ae  neg     rax
0x14000c1b1  sbb     rdx, rdx
0x14000c1b4  and     rdx, r12
0x14000c1b7  test    rcx, rcx
0x14000c1ba  jz      short loc_14000C1E3
0x14000c1bc  cmp     rdx, 3
0x14000c1c0  jb      short loc_14000C1E1
0x14000c1c2  dec     rdx
0x14000c1c5  mov     rax, r9
0x14000c1c8  cmp     rdx, r9
0x14000c1cb  jbe     short loc_14000C1E1
0x14000c1cd  mov     ecx, 23h ; '#'
0x14000c1d2  cmp     [r15+rax*2], cx
0x14000c1d7  jz      short loc_14000C236
0x14000c1d9  add     rax, r9
0x14000c1dc  cmp     rax, rdx
0x14000c1df  jb      short loc_14000C1D2
0x14000c1e1  mov     ebx, ebp
0x14000c1e3  test    ebx, ebx
0x14000c1e5  jnz     loc_14000C295
0x14000c1eb  mov     rsi, [rsp+88h+arg_10]
0x14000c1f3  mov     rdx, r10
0x14000c1f6  mov     r8d, [rsp+88h+arg_18]
0x14000c1fe  mov     [rsp+88h+var_60], r14
0x14000c203  mov     dword ptr [rsp+88h+MessageGuid], r13d
0x14000c208  mov     rcx, [rsi+30h]
0x14000c20c  mov     r9, [rsi+38h]
0x14000c210  mov     rax, [rcx]
0x14000c213  mov     rax, [rax+18h]
0x14000c217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c21c  mov     ebx, eax
0x14000c21e  test    eax, eax
0x14000c220  js      loc_14000C2C6
0x14000c226  mov     rax, [rsp+88h+arg_40]
0x14000c22e  mov     [rax], rsi
0x14000c231  jmp     loc_14000C2C6
0x14000c236  lea     rsi, [r15+2]
0x14000c23a  lea     rsi, [rsi+rax*2]
0x14000c23e  test    rsi, rsi
0x14000c241  jz      short loc_14000C2B8
0x14000c243  mov     edx, 200h
0x14000c248  mov     rax, rsi
0x14000c24b  mov     ecx, edx
0x14000c24d  cmp     [rax], r8w
0x14000c251  jz      short loc_14000C25C
0x14000c253  add     rax, 2
0x14000c257  sub     rcx, r9
0x14000c25a  jnz     short loc_14000C24D
0x14000c25c  mov     rax, rcx
0x14000c25f  neg     rax
0x14000c262  sbb     ebx, ebx
0x14000c264  not     ebx
0x14000c266  and     ebx, ebp
0x14000c268  test    rcx, rcx
0x14000c26b  jz      short loc_14000C295
0x14000c26d  sub     rdx, rcx
0x14000c270  neg     rcx
0x14000c273  sbb     rax, rax
0x14000c276  lea     rbp, [rdx+rdx]
0x14000c27a  and     rbp, rax
0x14000c27d  lea     rcx, [rbp+2]
0x14000c281  call    DAF_user_alloc
0x14000c286  mov     [rsp+88h+var_48], rax
0x14000c28b  test    rax, rax
0x14000c28e  jnz     short loc_14000C29F
0x14000c290  mov     ebx, 8007000Eh
0x14000c295  mov     rsi, [rsp+88h+arg_10]
0x14000c29d  jmp     short loc_14000C2C6
0x14000c29f  lea     r8, [rbp+2]; Size
0x14000c2a3  mov     rdx, rsi; Src
0x14000c2a6  mov     rcx, rax; void *
0x14000c2a9  call    memcpy_0
0x14000c2ae  mov     r10, [rsp+88h+var_48]
0x14000c2b3  jmp     loc_14000C1E3
0x14000c2b8  mov     ebx, ebp
0x14000c2ba  jmp     short loc_14000C295
0x14000c2bc  mov     ebx, 80070057h
0x14000c2c1  test    rdi, rdi
0x14000c2c4  jz      short loc_14000C2CE
0x14000c2c6  mov     rcx, rdi; void *
0x14000c2c9  call    MIDL_user_free
0x14000c2ce  mov     rax, [rsp+88h+var_48]
0x14000c2d3  test    rax, rax
0x14000c2d6  jz      short loc_14000C2E0
0x14000c2d8  mov     rcx, rax; void *
0x14000c2db  call    MIDL_user_free
0x14000c2e0  test    ebx, ebx
0x14000c2e2  jns     short loc_14000C2F1
0x14000c2e4  test    rsi, rsi
0x14000c2e7  jz      short loc_14000C2F1
0x14000c2e9  mov     rcx, rsi; lpMem
0x14000c2ec  call    ?RemoveAssociationEntry@@YAJPEAU_ASSOCIATION_ENTRY@@@Z; RemoveAssociationEntry(_ASSOCIATION_ENTRY *)
0x14000c2f1  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c2f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c2ff  jz      short loc_14000C327
0x14000c301  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c308  lea     rax, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000c30f  mov     r9d, 14h; int
0x14000c315  mov     dword ptr [rsp+88h+ExistingTokenHandle], ebx; char
0x14000c319  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x14000c31e  mov     rcx, [rcx+28h]; int
0x14000c322  call    WPP_RECORDER_SF_sd
0x14000c327  mov     eax, ebx
0x14000c329  mov     rbx, [rsp+88h+arg_0]
0x14000c331  add     rsp, 50h
0x14000c335  pop     r15
0x14000c337  pop     r14
0x14000c339  pop     r13
0x14000c33b  pop     r12
0x14000c33d  pop     rdi
0x14000c33e  pop     rsi
0x14000c33f  pop     rbp
0x14000c340  retn
```
