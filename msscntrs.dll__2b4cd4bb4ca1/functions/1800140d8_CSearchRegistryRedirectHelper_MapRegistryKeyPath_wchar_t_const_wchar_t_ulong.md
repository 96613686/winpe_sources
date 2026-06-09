# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x1800140d8`
- end: `0x1800142d0`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `504`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *this, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014008`

## callees

- `0x1800024a0`
- `0x180008b94`
- `0x1800095d8`
- `0x1800140d8`
- `0x180014420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014143`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001424a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014143`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001424a`

## string_xrefs

- `0x1800141b1`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x1800141ea`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        CSearchRegistryRedirectHelper *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v3; // rdi
  const WCHAR *v5; // rbx
  __int64 v6; // r8
  __int64 v8; // rsi
  __int64 v9; // rbp
  __int64 v10; // rax
  wchar_t *v11; // rdx
  __int64 v12; // r8
  wchar_t *v13; // rcx
  wchar_t *v14; // rdx
  unsigned int v15; // edi
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // esi
  __int64 v20; // rdx
  const WCHAR *v21; // r8
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR lpString2; // [rsp+30h] [rbp-68h] BYREF
  const WCHAR *v29; // [rsp+40h] [rbp-58h]
  int v30; // [rsp+48h] [rbp-50h]
  int v31; // [rsp+4Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = -1;
  v5 = a2;
  v6 = 69LL * *(_QWORD *)this;
  v8 = -1;
  v9 = LODWORD(off_1800212E0[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_1800212E0[v6 + 1], -1, 1) == 2 )
  {
    v10 = 2147483646;
    v11 = (wchar_t *)((char *)this + 8);
    v12 = 260;
    v13 = a3;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v15 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( v12 )
    {
      if ( (unsigned int)v8 <= (unsigned int)v9 )
        return 0;
      v17 = StringCchCatW(a3, (unsigned __int64)v14, &v5[v9]);
      v18 = v17;
      if ( v17 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v17,
          bIgnoreCase);
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)v15,
        bIgnoreCase);
      return v15;
    }
  }
  else
  {
    v19 = 0;
    lpString2.Ptr = (ULONGLONG)L"Software";
    *(_QWORD *)&lpString2.Size = L"System";
    while ( 1 )
    {
      v20 = -1;
      v21 = (const WCHAR *)*(&lpString2.Ptr + v19);
      do
        ++v20;
      while ( v21[v20] );
      if ( CompareStringOrdinal(v5, v20, v21, -1, 1) == 2 )
        break;
      if ( (unsigned int)++v19 >= 2 )
        return 2147500037LL;
    }
    if ( (byte_180022382 & 0x20) != 0 )
    {
      if ( v5 )
      {
        do
          ++v3;
        while ( v5[v3] );
        v26 = 2 * v3 + 2;
      }
      else
      {
        v26 = 10;
      }
      v30 = v26;
      v31 = 0;
      if ( !v5 )
        v5 = L"NULL";
      v29 = v5;
      McGenEventWrite_EventWriteTransfer(v23, v22, v24, v25, &lpString2);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800140d8  push    rbx
0x1800140da  push    rbp
0x1800140db  push    rsi
0x1800140dc  push    rdi
0x1800140dd  push    r12
0x1800140df  push    r14
0x1800140e1  push    r15
0x1800140e3  sub     rsp, 60h
0x1800140e7  mov     rax, cs:__security_cookie
0x1800140ee  xor     rax, rsp
0x1800140f1  mov     [rsp+98h+var_48], rax
0x1800140f6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800140fa  lea     rax, off_1800212E0; "WSearch"
0x180014101  mov     r14, r8
0x180014104  mov     rbx, rdx
0x180014107  imul    r8, [rcx], 228h
0x18001410e  mov     r15, rcx
0x180014111  mov     rsi, rdi
0x180014114  xor     r12d, r12d
0x180014117  mov     ebp, [r8+rax+10h]
0x18001411c  inc     rsi
0x18001411f  cmp     [rdx+rsi*2], r12w
0x180014124  jnz     short loc_18001411C
0x180014126  cmp     esi, ebp
0x180014128  jb      loc_18001420C
0x18001412e  mov     r8, [r8+rax+8]; lpString2
0x180014133  mov     r9d, edi; cchCount2
0x180014136  mov     edx, ebp; cchCount1
0x180014138  mov     [rsp+98h+bIgnoreCase], 1; int
0x180014140  mov     rcx, rbx; lpString1
0x180014143  call    cs:__imp_CompareStringOrdinal
0x180014149  cmp     eax, 2
0x18001414c  jnz     loc_18001420C
0x180014152  mov     eax, 7FFFFFFEh
0x180014157  lea     rdx, [r15+8]
0x18001415b  mov     r8d, 104h
0x180014161  mov     rcx, r14
0x180014164  test    rax, rax
0x180014167  jz      short loc_180014188
0x180014169  movzx   r9d, word ptr [rdx]
0x18001416d  test    r9w, r9w
0x180014171  jz      short loc_180014188
0x180014173  mov     [rcx], r9w
0x180014177  add     rdx, 2
0x18001417b  add     rcx, 2
0x18001417f  dec     rax
0x180014182  sub     r8, 1
0x180014186  jnz     short loc_180014164
0x180014188  mov     rax, r8
0x18001418b  lea     rdx, [rcx-2]
0x18001418f  neg     rax
0x180014192  sbb     edi, edi
0x180014194  not     edi
0x180014196  and     edi, 8007007Ah
0x18001419c  test    r8, r8
0x18001419f  cmovnz  rdx, rcx; unsigned __int64
0x1800141a3  mov     [rdx], r12w
0x1800141a7  jnz     short loc_1800141CC
0x1800141a9  mov     rcx, [rsp+98h]; this
0x1800141b1  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800141b8  mov     r9d, edi; char *
0x1800141bb  mov     edx, 46h ; 'F'; void *
0x1800141c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141c5  mov     eax, edi
0x1800141c7  jmp     loc_1800142B4
0x1800141cc  cmp     esi, ebp
0x1800141ce  jbe     short loc_180014205
0x1800141d0  lea     r8, [rbx+rbp*2]; wchar_t *
0x1800141d4  mov     rcx, r14; wchar_t *
0x1800141d7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800141dc  mov     ebx, eax
0x1800141de  test    eax, eax
0x1800141e0  jns     short loc_180014205
0x1800141e2  mov     rcx, [rsp+98h]; this
0x1800141ea  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800141f1  mov     r9d, eax; char *
0x1800141f4  mov     edx, 49h ; 'I'; void *
0x1800141f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141fe  mov     eax, ebx
0x180014200  jmp     loc_1800142B4
0x180014205  xor     eax, eax
0x180014207  jmp     loc_1800142B4
0x18001420c  lea     rax, aSoftware; "Software"
0x180014213  mov     esi, r12d
0x180014216  mov     [rsp+98h+lpString2], rax
0x18001421b  lea     rax, aSystem_0; "System"
0x180014222  mov     [rsp+98h+var_60], rax
0x180014227  movsxd  rax, esi
0x18001422a  mov     rdx, rdi
0x18001422d  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x180014232  inc     rdx; cchCount1
0x180014235  cmp     [r8+rdx*2], r12w
0x18001423a  jnz     short loc_180014232
0x18001423c  mov     r9d, edi; cchCount2
0x18001423f  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180014247  mov     rcx, rbx; lpString1
0x18001424a  call    cs:__imp_CompareStringOrdinal
0x180014250  cmp     eax, 2
0x180014253  jz      short loc_18001425E
0x180014255  inc     esi
0x180014257  cmp     esi, 2
0x18001425a  jb      short loc_180014227
0x18001425c  jmp     short loc_1800142AF
0x18001425e  test    cs:byte_180022382, 20h
0x180014265  jz      short loc_1800142AF
0x180014267  test    rbx, rbx
0x18001426a  jz      short loc_18001427F
0x18001426c  inc     rdi
0x18001426f  cmp     [rbx+rdi*2], r12w
0x180014274  jnz     short loc_18001426C
0x180014276  lea     edi, ds:2[rdi*2]
0x18001427d  jmp     short loc_180014284
0x18001427f  mov     edi, 0Ah
0x180014284  test    rbx, rbx
0x180014287  mov     [rsp+98h+var_50], edi
0x18001428b  lea     rax, aNull; "NULL"
0x180014292  mov     [rsp+98h+var_4C], r12d
0x180014297  cmovz   rbx, rax
0x18001429b  lea     rax, [rsp+98h+lpString2]
0x1800142a0  mov     qword ptr [rsp+98h+bIgnoreCase], rax; PEVENT_DATA_DESCRIPTOR
0x1800142a5  mov     [rsp+98h+var_58], rbx
0x1800142aa  call    McGenEventWrite_EventWriteTransfer
0x1800142af  mov     eax, 80004005h
0x1800142b4  mov     rcx, [rsp+98h+var_48]
0x1800142b9  xor     rcx, rsp; StackCookie
0x1800142bc  call    __security_check_cookie
0x1800142c1  add     rsp, 60h
0x1800142c5  pop     r15
0x1800142c7  pop     r14
0x1800142c9  pop     r12
0x1800142cb  pop     rdi
0x1800142cc  pop     rsi
0x1800142cd  pop     rbp
0x1800142ce  pop     rbx
0x1800142cf  retn
```
