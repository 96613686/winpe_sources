# CNamespaceHandle::ConstructKeyRootDirFromClass(CFileName &,ushort const *)

- ea: `0x1800080c0`
- end: `0x180008729`
- name: `?ConstructKeyRootDirFromClass@CNamespaceHandle@@IEAAJAEAVCFileName@@PEBG@Z`
- size: `1641`
- prototype: `__int64 __fastcall(__int16 **this, struct CFileName *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008730`
- `0x180014290`
- `0x18001e370`
- `0x1800246c4`
- `0x1800332dc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006d30`
- `0x1800080c0`
- `0x180016e90`
- `0x18001786c`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008249`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180008249`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008580`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000858c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008580`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000858c`
- `wbemcomn!?Transform@SHA256@@SAXPEAXIQEAE@Z` at `0x1800082d7`
- `wbemcomn!?Transform@SHA256@@SAXPEAXIQEAE@Z` at `0x1800082d7`
- `wbemcomn!GetMemLogObject` at `0x180008606`
- `wbemcomn!GetMemLogObject` at `0x18000864e`
- `wbemcomn!GetMemLogObject` at `0x1800086ce`
- `wbemcomn!GetMemLogObject` at `0x180008606`
- `wbemcomn!GetMemLogObject` at `0x18000864e`
- `wbemcomn!GetMemLogObject` at `0x1800086ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008611`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000865c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800086de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008611`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000865c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800086de`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ConstructKeyRootDirFromClass(
        __int16 **this,
        struct CFileName *a2,
        const unsigned __int16 *a3)
{
  int KeyRoot; // esi
  unsigned __int16 *v7; // r14
  __int64 v8; // r9
  __int64 v9; // rcx
  __int16 *v10; // r8
  __int64 v11; // rdx
  _WORD *v12; // rax
  __int16 v13; // r10
  _WORD *v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  wchar_t *v17; // r8
  const wchar_t *v18; // rax
  wchar_t v19; // cx
  wchar_t *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rdi
  __int64 v24; // rax
  unsigned int v25; // r15d
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rbp
  _WORD *v28; // r12
  unsigned int v29; // ebx
  unsigned int v30; // r15d
  __int64 v31; // rsi
  unsigned __int16 v32; // ax
  __int64 v33; // r8
  unsigned __int8 v34; // cl
  unsigned __int8 v35; // dl
  unsigned __int8 v36; // dl
  unsigned __int8 v37; // dl
  unsigned __int8 v38; // dl
  unsigned __int8 v39; // dl
  unsigned __int8 v40; // dl
  unsigned __int8 v41; // dl
  unsigned __int8 v42; // dl
  unsigned __int8 v43; // dl
  unsigned __int8 v44; // dl
  unsigned __int8 v45; // dl
  unsigned __int8 v46; // dl
  unsigned __int8 v47; // dl
  unsigned __int8 v48; // dl
  unsigned __int8 v49; // dl
  unsigned int v50; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v53; // rax
  CMemoryLog *v54; // rax
  unsigned __int16 *v55[3]; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int8 v56[32]; // [rsp+38h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( !a3 )
    return CNamespaceHandle::ConstructKeyRootDirFromKeyRoot((CNamespaceHandle *)this, a2, &qword_18004AEE0);
  v55[0] = 0;
  KeyRoot = CNamespaceHandle::GetKeyRoot((CNamespaceHandle *)this, a3, v55);
  if ( KeyRoot < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, KeyRoot);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        211,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)KeyRoot);
    }
    return (unsigned int)KeyRoot;
  }
  else
  {
    v7 = v55[0];
    if ( v55[0] )
    {
      v55[1] = v55[0];
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
      }
      v8 = 2147483646;
      v9 = 2147483646;
      v10 = this[9];
      v11 = 371;
      v12 = *(_WORD **)a2;
      do
      {
        if ( !v9 )
          break;
        v13 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v12++ = v13;
        --v9;
        --v11;
      }
      while ( v11 );
      v14 = v12 - 1;
      if ( v11 )
        v14 = v12;
      *v14 = 0;
      *(_WORD *)(*(_QWORD *)a2 + 2LL * *((int *)this + 20)) = 92;
      v15 = *((int *)this + 20);
      v16 = (unsigned int)(370 - v15);
      if ( (_DWORD)v15 != 370 )
      {
        v17 = (wchar_t *)(*(_QWORD *)a2 + 2LL + 2 * v15);
        if ( v16 > 0x7FFFFFFF )
        {
          *v17 = 0;
        }
        else
        {
          v18 = L"KI_";
          do
          {
            if ( !v8 )
              break;
            v19 = *v18;
            if ( !*v18 )
              break;
            ++v18;
            *v17++ = v19;
            --v8;
            --v16;
          }
          while ( v16 );
          v20 = v17 - 1;
          if ( v16 )
            v20 = v17;
          *v20 = 0;
        }
      }
      v21 = *((int *)this + 20);
      v22 = *(_QWORD *)a2;
      v23 = -1;
      v24 = -1;
      do
        ++v24;
      while ( v7[v24] );
      v25 = 2 * v24 + 2;
      v26 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v25, 2u));
      v27 = v26;
      if ( v26 )
      {
        v28 = (_WORD *)(v22 + 2 * (v21 + 4));
        v55[2] = v26;
        if ( v25 > 1 )
        {
          v29 = 0;
          v30 = v25 - 1;
          do
          {
            v31 = (int)v29;
            v32 = v7[v31];
            if ( !v32 )
              break;
            if ( (unsigned __int16)(v32 - 97) > 0x19u )
            {
              if ( v32 >= 0x80u )
                v32 = wbem_towupper(v32);
            }
            else
            {
              v32 -= 32;
            }
            v27[v31] = v32;
            ++v29;
          }
          while ( v29 < v30 );
          v27[v29] = 0;
        }
        do
          ++v23;
        while ( v27[v23] );
        SHA256::Transform(v27, 2 * v23, v56);
        v33 = 0;
        do
        {
          v34 = v56[v33];
          *v28 = a0123456789abcd[(unsigned __int64)v34 >> 4];
          v28[1] = a0123456789abcd[v34 & 0xF];
          v35 = v56[(unsigned int)(v33 + 1)];
          v28[2] = a0123456789abcd[(unsigned __int64)v35 >> 4];
          v28[3] = a0123456789abcd[v35 & 0xF];
          v36 = v56[(unsigned int)(v33 + 2)];
          v28[4] = a0123456789abcd[(unsigned __int64)v36 >> 4];
          v28[5] = a0123456789abcd[v36 & 0xF];
          v37 = v56[(unsigned int)(v33 + 3)];
          v28[6] = a0123456789abcd[(unsigned __int64)v37 >> 4];
          v28[7] = a0123456789abcd[v37 & 0xF];
          v38 = v56[(unsigned int)(v33 + 4)];
          v28[8] = a0123456789abcd[(unsigned __int64)v38 >> 4];
          v28[9] = a0123456789abcd[v38 & 0xF];
          v39 = v56[(unsigned int)(v33 + 5)];
          v28[10] = a0123456789abcd[(unsigned __int64)v39 >> 4];
          v28[11] = a0123456789abcd[v39 & 0xF];
          v40 = v56[(unsigned int)(v33 + 6)];
          v28[12] = a0123456789abcd[(unsigned __int64)v40 >> 4];
          v28[13] = a0123456789abcd[v40 & 0xF];
          v41 = v56[(unsigned int)(v33 + 7)];
          v28[14] = a0123456789abcd[(unsigned __int64)v41 >> 4];
          v28[15] = a0123456789abcd[v41 & 0xF];
          v42 = v56[(unsigned int)(v33 + 8)];
          v28[16] = a0123456789abcd[(unsigned __int64)v42 >> 4];
          v28[17] = a0123456789abcd[v42 & 0xF];
          v43 = v56[(unsigned int)(v33 + 9)];
          v28[18] = a0123456789abcd[(unsigned __int64)v43 >> 4];
          v28[19] = a0123456789abcd[v43 & 0xF];
          v44 = v56[(unsigned int)(v33 + 10)];
          v28[20] = a0123456789abcd[(unsigned __int64)v44 >> 4];
          v28[21] = a0123456789abcd[v44 & 0xF];
          v45 = v56[(unsigned int)(v33 + 11)];
          v28[22] = a0123456789abcd[(unsigned __int64)v45 >> 4];
          v28[23] = a0123456789abcd[v45 & 0xF];
          v46 = v56[(unsigned int)(v33 + 12)];
          v28[24] = a0123456789abcd[(unsigned __int64)v46 >> 4];
          v28[25] = a0123456789abcd[v46 & 0xF];
          v47 = v56[(unsigned int)(v33 + 13)];
          v28[26] = a0123456789abcd[(unsigned __int64)v47 >> 4];
          v28[27] = a0123456789abcd[v47 & 0xF];
          v48 = v56[(unsigned int)(v33 + 14)];
          v28[28] = a0123456789abcd[(unsigned __int64)v48 >> 4];
          v28[29] = a0123456789abcd[v48 & 0xF];
          v49 = v56[(unsigned int)(v33 + 15)];
          v28[30] = a0123456789abcd[(unsigned __int64)v49 >> 4];
          v28[31] = a0123456789abcd[v49 & 0xF];
          v28 += 32;
          v33 = (unsigned int)(v33 + 16);
        }
        while ( (unsigned int)v33 < 0x20 );
        *v28 = 0;
        CWin32DefaultArena::WbemMemFree(v27);
        v50 = 0;
      }
      else
      {
        v54 = GetMemLogObject();
        v50 = -2147217402;
        CMemoryLog::Write(v54, -2147217402);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            214,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749894LL);
        }
      }
      CWin32DefaultArena::WbemMemFree(v7);
      return v50;
    }
    else
    {
      v53 = GetMemLogObject();
      CMemoryLog::Write(v53, -2147217392);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          212,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749904LL);
      }
      return 2147749904LL;
    }
  }
}

```

## disassembly

```asm
0x1800080c0  mov     [rsp+arg_18], rbx
0x1800080c5  push    rbp
0x1800080c6  push    rsi
0x1800080c7  push    rdi
0x1800080c8  push    r12
0x1800080ca  push    r13
0x1800080cc  push    r14
0x1800080ce  push    r15
0x1800080d0  sub     rsp, 60h
0x1800080d4  mov     rax, cs:__security_cookie
0x1800080db  xor     rax, rsp
0x1800080de  mov     [rsp+98h+var_40], rax
0x1800080e3  mov     rsi, r8
0x1800080e6  mov     rdi, rdx
0x1800080e9  mov     rbx, rcx
0x1800080ec  lea     r12, WPP_GLOBAL_Control
0x1800080f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080fa  cmp     rcx, r12
0x1800080fd  jz      short loc_180008109
0x1800080ff  test    byte ptr [rcx+1Ch], 1
0x180008103  jnz     loc_1800085E2
0x180008109  mov     rcx, rbx; this
0x18000810c  test    rsi, rsi
0x18000810f  jz      loc_1800085D1
0x180008115  mov     [rsp+98h+var_78], 0
0x18000811e  lea     r8, [rsp+98h+var_78]; unsigned __int16 **
0x180008123  mov     rdx, rsi; unsigned __int16 *
0x180008126  call    ?GetKeyRoot@CNamespaceHandle@@IEAAJPEBGPEAPEAG@Z; CNamespaceHandle::GetKeyRoot(ushort const *,ushort * *)
0x18000812b  mov     esi, eax
0x18000812d  test    eax, eax
0x18000812f  js      loc_180008606
0x180008135  mov     r14, [rsp+98h+var_78]
0x18000813a  test    r14, r14
0x18000813d  jz      loc_18000864E
0x180008143  mov     [rsp+98h+var_70], r14
0x180008148  mov     rcx, cs:WPP_GLOBAL_Control
0x18000814f  cmp     rcx, r12
0x180008152  jz      short loc_18000815E
0x180008154  test    byte ptr [rcx+1Ch], 1
0x180008158  jnz     loc_18000869F
0x18000815e  mov     r9d, 7FFFFFFEh
0x180008164  mov     ecx, r9d
0x180008167  mov     r8, [rbx+48h]
0x18000816b  mov     edx, 173h
0x180008170  mov     rax, [rdi]
0x180008173  test    rcx, rcx
0x180008176  jz      short loc_180008197
0x180008178  movzx   r10d, word ptr [r8]
0x18000817c  test    r10w, r10w
0x180008180  jz      short loc_180008197
0x180008182  add     r8, 2
0x180008186  mov     [rax], r10w
0x18000818a  add     rax, 2
0x18000818e  dec     rcx
0x180008191  sub     rdx, 1
0x180008195  jnz     short loc_180008173
0x180008197  lea     rcx, [rax-2]
0x18000819b  test    rdx, rdx
0x18000819e  cmovnz  rcx, rax
0x1800081a2  xor     eax, eax
0x1800081a4  mov     [rcx], ax
0x1800081a7  movsxd  rcx, dword ptr [rbx+50h]
0x1800081ab  mov     rax, [rdi]
0x1800081ae  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x1800081b4  movsxd  rcx, dword ptr [rbx+50h]
0x1800081b8  mov     edx, 172h
0x1800081bd  sub     edx, ecx
0x1800081bf  jz      short loc_180008212
0x1800081c1  mov     rax, [rdi]
0x1800081c4  add     rax, 2
0x1800081c8  lea     r8, [rax+rcx*2]
0x1800081cc  cmp     rdx, 7FFFFFFFh
0x1800081d3  ja      loc_1800086C3
0x1800081d9  lea     rax, aKi_0; "KI_"
0x1800081e0  test    r9, r9
0x1800081e3  jz      short loc_180008202
0x1800081e5  movzx   ecx, word ptr [rax]
0x1800081e8  test    cx, cx
0x1800081eb  jz      short loc_180008202
0x1800081ed  add     rax, 2
0x1800081f1  mov     [r8], cx
0x1800081f5  add     r8, 2
0x1800081f9  dec     r9
0x1800081fc  sub     rdx, 1
0x180008200  jnz     short loc_1800081E0
0x180008202  lea     rcx, [r8-2]
0x180008206  test    rdx, rdx
0x180008209  cmovnz  rcx, r8
0x18000820d  xor     eax, eax
0x18000820f  mov     [rcx], ax
0x180008212  movsxd  rbx, dword ptr [rbx+50h]
0x180008216  mov     rsi, [rdi]
0x180008219  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180008220  mov     rax, rdi
0x180008223  lea     rax, [rax+1]
0x180008227  cmp     word ptr [r14+rax*2], 0
0x18000822d  jnz     short loc_180008223
0x18000822f  lea     r15d, ds:2[rax*2]
0x180008237  mov     ecx, r15d
0x18000823a  mov     eax, 2
0x18000823f  mul     rcx
0x180008242  cmovb   rax, rdi
0x180008246  mov     rcx, rax
0x180008249  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000824f  mov     rbp, rax
0x180008252  test    rax, rax
0x180008255  jz      loc_1800086CE
0x18000825b  lea     r12, [rbx+4]
0x18000825f  lea     r12, [rsi+r12*2]
0x180008263  mov     [rsp+98h+var_68], rax
0x180008268  cmp     r15d, 1
0x18000826c  jbe     short loc_1800082C0
0x18000826e  xor     ebx, ebx
0x180008270  dec     r15d
0x180008273  mov     r13d, 80h
0x180008279  nop     dword ptr [rax+00000000h]
0x180008280  movsxd  rax, ebx
0x180008283  lea     rsi, [rax+rax]
0x180008287  movzx   eax, word ptr [r14+rsi]
0x18000828c  test    ax, ax
0x18000828f  jz      short loc_1800082AD
0x180008291  lea     ecx, [rax-61h]
0x180008294  cmp     cx, 19h
0x180008298  ja      loc_1800085BA
0x18000829e  sub     ax, 20h ; ' '
0x1800082a2  mov     [rsi+rbp], ax
0x1800082a6  inc     ebx
0x1800082a8  cmp     ebx, r15d
0x1800082ab  jb      short loc_180008280
0x1800082ad  movsxd  rax, ebx
0x1800082b0  lea     rcx, [rax+rax]
0x1800082b4  xor     eax, eax
0x1800082b6  mov     [rcx+rbp], ax
0x1800082ba  nop     word ptr [rax+rax+00h]
0x1800082c0  lea     rdi, [rdi+1]
0x1800082c4  cmp     word ptr [rbp+rdi*2+0], 0
0x1800082ca  jnz     short loc_1800082C0
0x1800082cc  lea     edx, [rdi+rdi]
0x1800082cf  lea     r8, [rsp+98h+var_60]
0x1800082d4  mov     rcx, rbp
0x1800082d7  call    cs:__imp_?Transform@SHA256@@SAXPEAXIQEAE@Z; SHA256::Transform(void *,uint,uchar * const)
0x1800082dd  xor     r8d, r8d
0x1800082e0  lea     r9, a0123456789abcd; "0123456789ABCDEF"
0x1800082e7  movzx   ecx, [rsp+r8+98h+var_60]
0x1800082ed  mov     eax, ecx
0x1800082ef  shr     rax, 4
0x1800082f3  movzx   eax, word ptr [r9+rax*2]
0x1800082f8  mov     [r12], ax
0x1800082fd  and     ecx, 0Fh
0x180008300  movzx   eax, word ptr [r9+rcx*2]
0x180008305  mov     [r12+2], ax
0x18000830b  lea     eax, [r8+1]
0x18000830f  movzx   edx, [rsp+rax+98h+var_60]
0x180008314  mov     eax, edx
0x180008316  shr     rax, 4
0x18000831a  movzx   eax, word ptr [r9+rax*2]
0x18000831f  mov     [r12+4], ax
0x180008325  and     edx, 0Fh
0x180008328  movzx   eax, word ptr [r9+rdx*2]
0x18000832d  mov     [r12+6], ax
0x180008333  lea     eax, [r8+2]
0x180008337  movzx   edx, [rsp+rax+98h+var_60]
0x18000833c  mov     eax, edx
0x18000833e  shr     rax, 4
0x180008342  movzx   eax, word ptr [r9+rax*2]
0x180008347  mov     [r12+8], ax
0x18000834d  and     edx, 0Fh
0x180008350  movzx   eax, word ptr [r9+rdx*2]
0x180008355  mov     [r12+0Ah], ax
0x18000835b  lea     eax, [r8+3]
0x18000835f  movzx   edx, [rsp+rax+98h+var_60]
0x180008364  mov     eax, edx
0x180008366  shr     rax, 4
0x18000836a  movzx   eax, word ptr [r9+rax*2]
0x18000836f  mov     [r12+0Ch], ax
0x180008375  and     edx, 0Fh
0x180008378  movzx   eax, word ptr [r9+rdx*2]
0x18000837d  mov     [r12+0Eh], ax
0x180008383  lea     eax, [r8+4]
0x180008387  movzx   edx, [rsp+rax+98h+var_60]
0x18000838c  mov     eax, edx
0x18000838e  shr     rax, 4
0x180008392  movzx   eax, word ptr [r9+rax*2]
0x180008397  mov     [r12+10h], ax
0x18000839d  and     edx, 0Fh
0x1800083a0  movzx   eax, word ptr [r9+rdx*2]
0x1800083a5  mov     [r12+12h], ax
0x1800083ab  lea     eax, [r8+5]
0x1800083af  movzx   edx, [rsp+rax+98h+var_60]
0x1800083b4  mov     eax, edx
0x1800083b6  shr     rax, 4
0x1800083ba  movzx   eax, word ptr [r9+rax*2]
0x1800083bf  mov     [r12+14h], ax
0x1800083c5  and     edx, 0Fh
0x1800083c8  movzx   eax, word ptr [r9+rdx*2]
0x1800083cd  mov     [r12+16h], ax
0x1800083d3  lea     eax, [r8+6]
0x1800083d7  movzx   edx, [rsp+rax+98h+var_60]
0x1800083dc  mov     eax, edx
0x1800083de  shr     rax, 4
0x1800083e2  movzx   eax, word ptr [r9+rax*2]
0x1800083e7  mov     [r12+18h], ax
0x1800083ed  and     edx, 0Fh
0x1800083f0  movzx   eax, word ptr [r9+rdx*2]
0x1800083f5  mov     [r12+1Ah], ax
0x1800083fb  lea     eax, [r8+7]
0x1800083ff  movzx   edx, [rsp+rax+98h+var_60]
0x180008404  mov     eax, edx
0x180008406  shr     rax, 4
0x18000840a  movzx   eax, word ptr [r9+rax*2]
0x18000840f  mov     [r12+1Ch], ax
0x180008415  and     edx, 0Fh
0x180008418  movzx   eax, word ptr [r9+rdx*2]
0x18000841d  mov     [r12+1Eh], ax
0x180008423  lea     eax, [r8+8]
0x180008427  movzx   edx, [rsp+rax+98h+var_60]
0x18000842c  mov     eax, edx
0x18000842e  shr     rax, 4
0x180008432  movzx   eax, word ptr [r9+rax*2]
0x180008437  mov     [r12+20h], ax
0x18000843d  and     edx, 0Fh
0x180008440  movzx   eax, word ptr [r9+rdx*2]
0x180008445  mov     [r12+22h], ax
0x18000844b  lea     eax, [r8+9]
0x18000844f  movzx   edx, [rsp+rax+98h+var_60]
0x180008454  mov     eax, edx
0x180008456  shr     rax, 4
0x18000845a  movzx   eax, word ptr [r9+rax*2]
0x18000845f  mov     [r12+24h], ax
0x180008465  and     edx, 0Fh
0x180008468  movzx   eax, word ptr [r9+rdx*2]
0x18000846d  mov     [r12+26h], ax
0x180008473  lea     eax, [r8+0Ah]
0x180008477  movzx   edx, [rsp+rax+98h+var_60]
0x18000847c  mov     eax, edx
0x18000847e  shr     rax, 4
0x180008482  movzx   eax, word ptr [r9+rax*2]
0x180008487  mov     [r12+28h], ax
0x18000848d  and     edx, 0Fh
0x180008490  movzx   eax, word ptr [r9+rdx*2]
0x180008495  mov     [r12+2Ah], ax
0x18000849b  lea     eax, [r8+0Bh]
0x18000849f  movzx   edx, [rsp+rax+98h+var_60]
0x1800084a4  mov     eax, edx
0x1800084a6  shr     rax, 4
0x1800084aa  movzx   eax, word ptr [r9+rax*2]
0x1800084af  mov     [r12+2Ch], ax
0x1800084b5  and     edx, 0Fh
0x1800084b8  movzx   eax, word ptr [r9+rdx*2]
0x1800084bd  mov     [r12+2Eh], ax
0x1800084c3  lea     eax, [r8+0Ch]
0x1800084c7  movzx   edx, [rsp+rax+98h+var_60]
0x1800084cc  mov     eax, edx
0x1800084ce  shr     rax, 4
0x1800084d2  movzx   eax, word ptr [r9+rax*2]
0x1800084d7  mov     [r12+30h], ax
0x1800084dd  and     edx, 0Fh
0x1800084e0  movzx   eax, word ptr [r9+rdx*2]
0x1800084e5  mov     [r12+32h], ax
0x1800084eb  lea     eax, [r8+0Dh]
0x1800084ef  movzx   edx, [rsp+rax+98h+var_60]
0x1800084f4  mov     eax, edx
0x1800084f6  shr     rax, 4
0x1800084fa  movzx   eax, word ptr [r9+rax*2]
0x1800084ff  mov     [r12+34h], ax
0x180008505  and     edx, 0Fh
0x180008508  movzx   eax, word ptr [r9+rdx*2]
0x18000850d  mov     [r12+36h], ax
0x180008513  lea     eax, [r8+0Eh]
0x180008517  movzx   edx, [rsp+rax+98h+var_60]
0x18000851c  mov     eax, edx
0x18000851e  shr     rax, 4
0x180008522  movzx   eax, word ptr [r9+rax*2]
0x180008527  mov     [r12+38h], ax
0x18000852d  and     edx, 0Fh
0x180008530  movzx   eax, word ptr [r9+rdx*2]
0x180008535  mov     [r12+3Ah], ax
0x18000853b  lea     eax, [r8+0Fh]
0x18000853f  movzx   edx, [rsp+rax+98h+var_60]
0x180008544  mov     eax, edx
0x180008546  shr     rax, 4
0x18000854a  movzx   eax, word ptr [r9+rax*2]
0x18000854f  mov     [r12+3Ch], ax
0x180008555  and     edx, 0Fh
0x180008558  movzx   eax, word ptr [r9+rdx*2]
0x18000855d  mov     [r12+3Eh], ax
0x180008563  lea     r12, [r12+40h]
0x180008568  add     r8d, 10h
0x18000856c  cmp     r8d, 20h ; ' '
0x180008570  jb      loc_1800082E7
0x180008576  xor     eax, eax
0x180008578  mov     [r12], ax
0x18000857d  mov     rcx, rbp
0x180008580  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008586  nop
0x180008587  xor     ebx, ebx
0x180008589  mov     rcx, r14
0x18000858c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008592  nop
0x180008593  mov     eax, ebx
  ... truncated ...
```
