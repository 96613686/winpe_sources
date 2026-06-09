# CClipBase::RemoveNotificationSinks(void)

- ea: `0x140055100`
- end: `0x14005542d`
- name: `?RemoveNotificationSinks@CClipBase@@MEAAJXZ`
- size: `813`
- prototype: `__int64 __fastcall(CClipBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003de20`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x140055100`
- `0x14006b010`

## string_xrefs

- `0x140055167`: `Failed to remove FORMAT_LIST_RESPONSE event sink!`
- `0x140055241`: `Failed to remove FORMAT_DATA_RESPONSE event sink!`
- `0x1400551d4`: `Failed to remove FORMAT_DATA_REQUEST event sink!`
- `0x14005531b`: `Failed to remove FILE_CONTENTS_RESPONSE event sink!`
- `0x1400552ae`: `Failed to remove FILE_CONTENTS_REQUEST event sink!`
- `0x1400553f5`: `Failed to remove UNLOCK_CLIPDATA event sink!`
- `0x140055388`: `Failed to remove LOCK_CLIPDATA event sink!`

## pseudocode

```c
__int64 __fastcall CClipBase::RemoveNotificationSinks(CClipBase *this)
{
  __int64 v2; // rcx
  int v3; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edi
  unsigned int v6; // eax
  int v7; // edi
  unsigned int v8; // eax
  int v9; // edi
  unsigned int v10; // eax
  int v11; // edi
  unsigned int v12; // eax
  int v13; // edi
  unsigned int v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  __int64 v18; // [rsp+28h] [rbp-30h]
  int v19; // [rsp+28h] [rbp-30h]

  v2 = *((_QWORD *)this + 85);
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v2 + 96LL))(v2, 156, (char *)this + 128);
    if ( v3 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = v3;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to remove FORMAT_LIST_RESPONSE event sink!",
        v19);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
           *((_QWORD *)this + 85),
           157,
           (char *)this + 136);
    if ( v5 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v5;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v6,
        (__int64)"Failed to remove FORMAT_DATA_REQUEST event sink!",
        v18);
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
           *((_QWORD *)this + 85),
           158,
           (char *)this + 144);
    if ( v7 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v7;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v8,
        (__int64)"Failed to remove FORMAT_DATA_RESPONSE event sink!",
        v18);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
           *((_QWORD *)this + 85),
           159,
           (char *)this + 152);
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v9;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v10,
        (__int64)"Failed to remove FILE_CONTENTS_REQUEST event sink!",
        v18);
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
            *((_QWORD *)this + 85),
            160,
            (char *)this + 160);
    if ( v11 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v11;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v12,
        (__int64)"Failed to remove FILE_CONTENTS_RESPONSE event sink!",
        v18);
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
            *((_QWORD *)this + 85),
            164,
            (char *)this + 168);
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v13;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v14,
        (__int64)"Failed to remove LOCK_CLIPDATA event sink!",
        v18);
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
            *((_QWORD *)this + 85),
            165,
            (char *)this + 176);
    if ( v15 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v18) = v15;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v16,
        (__int64)"Failed to remove UNLOCK_CLIPDATA event sink!",
        v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140055100  push    rbx
0x140055102  push    rdi
0x140055103  push    r14
0x140055105  push    r15
0x140055107  sub     rsp, 38h
0x14005510b  mov     rbx, rcx
0x14005510e  mov     rcx, [rcx+2A8h]
0x140055115  test    rcx, rcx
0x140055118  jz      loc_140055420
0x14005511e  mov     rax, [rcx]
0x140055121  lea     r8, [rbx+80h]
0x140055128  mov     edx, 9Ch
0x14005512d  mov     rax, [rax+60h]
0x140055131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055136  lea     r15, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005513d  mov     edi, eax
0x14005513f  lea     r14, WPP_GLOBAL_Control
0x140055146  test    eax, eax
0x140055148  jns     short loc_140055192
0x14005514a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055151  cmp     rcx, r14
0x140055154  jz      short loc_140055192
0x140055156  test    byte ptr [rcx+1Ch], 8
0x14005515a  jz      short loc_140055192
0x14005515c  cmp     byte ptr [rcx+19h], 2
0x140055160  jb      short loc_140055192
0x140055162  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055167  lea     rcx, aFailedToRemove_9; "Failed to remove FORMAT_LIST_RESPONSE e"...
0x14005516e  mov     dword ptr [rsp+58h+var_30], edi
0x140055172  mov     [rsp+58h+var_38], rcx
0x140055177  mov     edx, 2Bh ; '+'
0x14005517c  mov     rcx, cs:WPP_GLOBAL_Control
0x140055183  mov     r9d, eax
0x140055186  mov     r8, r15
0x140055189  mov     rcx, [rcx+10h]
0x14005518d  call    WPP_SF_DsD
0x140055192  mov     rcx, [rbx+2A8h]
0x140055199  lea     r8, [rbx+88h]
0x1400551a0  mov     edx, 9Dh
0x1400551a5  mov     rax, [rcx]
0x1400551a8  mov     rax, [rax+60h]
0x1400551ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400551b1  mov     edi, eax
0x1400551b3  test    eax, eax
0x1400551b5  jns     short loc_1400551FF
0x1400551b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400551be  cmp     rcx, r14
0x1400551c1  jz      short loc_1400551FF
0x1400551c3  test    byte ptr [rcx+1Ch], 8
0x1400551c7  jz      short loc_1400551FF
0x1400551c9  cmp     byte ptr [rcx+19h], 2
0x1400551cd  jb      short loc_1400551FF
0x1400551cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400551d4  lea     rcx, aFailedToRemove_14; "Failed to remove FORMAT_DATA_REQUEST ev"...
0x1400551db  mov     dword ptr [rsp+58h+var_30], edi
0x1400551df  mov     [rsp+58h+var_38], rcx
0x1400551e4  mov     edx, 2Ch ; ','
0x1400551e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400551f0  mov     r9d, eax
0x1400551f3  mov     r8, r15
0x1400551f6  mov     rcx, [rcx+10h]
0x1400551fa  call    WPP_SF_DsD
0x1400551ff  mov     rcx, [rbx+2A8h]
0x140055206  lea     r8, [rbx+90h]
0x14005520d  mov     edx, 9Eh
0x140055212  mov     rax, [rcx]
0x140055215  mov     rax, [rax+60h]
0x140055219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005521e  mov     edi, eax
0x140055220  test    eax, eax
0x140055222  jns     short loc_14005526C
0x140055224  mov     rcx, cs:WPP_GLOBAL_Control
0x14005522b  cmp     rcx, r14
0x14005522e  jz      short loc_14005526C
0x140055230  test    byte ptr [rcx+1Ch], 8
0x140055234  jz      short loc_14005526C
0x140055236  cmp     byte ptr [rcx+19h], 2
0x14005523a  jb      short loc_14005526C
0x14005523c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055241  lea     rcx, aFailedToRemove_19; "Failed to remove FORMAT_DATA_RESPONSE e"...
0x140055248  mov     dword ptr [rsp+58h+var_30], edi
0x14005524c  mov     [rsp+58h+var_38], rcx
0x140055251  mov     edx, 2Dh ; '-'
0x140055256  mov     rcx, cs:WPP_GLOBAL_Control
0x14005525d  mov     r9d, eax
0x140055260  mov     r8, r15
0x140055263  mov     rcx, [rcx+10h]
0x140055267  call    WPP_SF_DsD
0x14005526c  mov     rcx, [rbx+2A8h]
0x140055273  lea     r8, [rbx+98h]
0x14005527a  mov     edx, 9Fh
0x14005527f  mov     rax, [rcx]
0x140055282  mov     rax, [rax+60h]
0x140055286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005528b  mov     edi, eax
0x14005528d  test    eax, eax
0x14005528f  jns     short loc_1400552D9
0x140055291  mov     rcx, cs:WPP_GLOBAL_Control
0x140055298  cmp     rcx, r14
0x14005529b  jz      short loc_1400552D9
0x14005529d  test    byte ptr [rcx+1Ch], 8
0x1400552a1  jz      short loc_1400552D9
0x1400552a3  cmp     byte ptr [rcx+19h], 2
0x1400552a7  jb      short loc_1400552D9
0x1400552a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400552ae  lea     rcx, aFailedToRemove_5; "Failed to remove FILE_CONTENTS_REQUEST "...
0x1400552b5  mov     dword ptr [rsp+58h+var_30], edi
0x1400552b9  mov     [rsp+58h+var_38], rcx
0x1400552be  mov     edx, 2Eh ; '.'
0x1400552c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400552ca  mov     r9d, eax
0x1400552cd  mov     r8, r15
0x1400552d0  mov     rcx, [rcx+10h]
0x1400552d4  call    WPP_SF_DsD
0x1400552d9  mov     rcx, [rbx+2A8h]
0x1400552e0  lea     r8, [rbx+0A0h]
0x1400552e7  mov     edx, 0A0h
0x1400552ec  mov     rax, [rcx]
0x1400552ef  mov     rax, [rax+60h]
0x1400552f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400552f8  mov     edi, eax
0x1400552fa  test    eax, eax
0x1400552fc  jns     short loc_140055346
0x1400552fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140055305  cmp     rcx, r14
0x140055308  jz      short loc_140055346
0x14005530a  test    byte ptr [rcx+1Ch], 8
0x14005530e  jz      short loc_140055346
0x140055310  cmp     byte ptr [rcx+19h], 2
0x140055314  jb      short loc_140055346
0x140055316  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005531b  lea     rcx, aFailedToRemove_22; "Failed to remove FILE_CONTENTS_RESPONSE"...
0x140055322  mov     dword ptr [rsp+58h+var_30], edi
0x140055326  mov     [rsp+58h+var_38], rcx
0x14005532b  mov     edx, 2Fh ; '/'
0x140055330  mov     rcx, cs:WPP_GLOBAL_Control
0x140055337  mov     r9d, eax
0x14005533a  mov     r8, r15
0x14005533d  mov     rcx, [rcx+10h]
0x140055341  call    WPP_SF_DsD
0x140055346  mov     rcx, [rbx+2A8h]
0x14005534d  lea     r8, [rbx+0A8h]
0x140055354  mov     edx, 0A4h
0x140055359  mov     rax, [rcx]
0x14005535c  mov     rax, [rax+60h]
0x140055360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055365  mov     edi, eax
0x140055367  test    eax, eax
0x140055369  jns     short loc_1400553B3
0x14005536b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055372  cmp     rcx, r14
0x140055375  jz      short loc_1400553B3
0x140055377  test    byte ptr [rcx+1Ch], 8
0x14005537b  jz      short loc_1400553B3
0x14005537d  cmp     byte ptr [rcx+19h], 2
0x140055381  jb      short loc_1400553B3
0x140055383  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055388  lea     rcx, aFailedToRemove; "Failed to remove LOCK_CLIPDATA event si"...
0x14005538f  mov     dword ptr [rsp+58h+var_30], edi
0x140055393  mov     [rsp+58h+var_38], rcx
0x140055398  mov     edx, 30h ; '0'
0x14005539d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400553a4  mov     r9d, eax
0x1400553a7  mov     r8, r15
0x1400553aa  mov     rcx, [rcx+10h]
0x1400553ae  call    WPP_SF_DsD
0x1400553b3  mov     rcx, [rbx+2A8h]
0x1400553ba  lea     r8, [rbx+0B0h]
0x1400553c1  mov     edx, 0A5h
0x1400553c6  mov     rax, [rcx]
0x1400553c9  mov     rax, [rax+60h]
0x1400553cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400553d2  mov     ebx, eax
0x1400553d4  test    eax, eax
0x1400553d6  jns     short loc_140055420
0x1400553d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400553df  cmp     rcx, r14
0x1400553e2  jz      short loc_140055420
0x1400553e4  test    byte ptr [rcx+1Ch], 8
0x1400553e8  jz      short loc_140055420
0x1400553ea  cmp     byte ptr [rcx+19h], 2
0x1400553ee  jb      short loc_140055420
0x1400553f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400553f5  lea     rcx, aFailedToRemove_2; "Failed to remove UNLOCK_CLIPDATA event "...
0x1400553fc  mov     dword ptr [rsp+58h+var_30], ebx
0x140055400  mov     [rsp+58h+var_38], rcx
0x140055405  mov     edx, 31h ; '1'
0x14005540a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055411  mov     r9d, eax
0x140055414  mov     r8, r15
0x140055417  mov     rcx, [rcx+10h]
0x14005541b  call    WPP_SF_DsD
0x140055420  xor     eax, eax
0x140055422  add     rsp, 38h
0x140055426  pop     r15
0x140055428  pop     r14
0x14005542a  pop     rdi
0x14005542b  pop     rbx
0x14005542c  retn
```
