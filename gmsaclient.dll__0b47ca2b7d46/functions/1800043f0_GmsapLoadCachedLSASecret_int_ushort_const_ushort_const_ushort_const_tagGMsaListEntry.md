# GmsapLoadCachedLSASecret(int,ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)

- ea: `0x1800043f0`
- end: `0x180004613`
- name: `?GmsapLoadCachedLSASecret@@YAJHPEBG00PEAPEAU_tagGMsaListEntry@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _tagGMsaListEntry **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002e18`

## callees

- `0x180002380`
- `0x1800043f0`
- `0x180004bbc`
- `0x180006280`
- `0x1800062b0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c9`

## pseudocode

```c
__int64 __fastcall GmsapLoadCachedLSASecret(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _tagGMsaListEntry **a5)
{
  struct _tagPasswordData *v6; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int8 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  struct _tagPasswordData *v18; // rcx
  size_t Size; // [rsp+30h] [rbp-28h] BYREF
  struct _tagPasswordData *v21; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *Src; // [rsp+40h] [rbp-18h] BYREF

  Size = 0;
  v6 = 0;
  Src = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  *a5 = 0;
  v10 = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, size_t *, unsigned __int8 **))xmmword_18000B5B0)(
          0,
          a2,
          a3,
          &Size,
          &Src);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v14 = GmsapParsePasswordData((unsigned int)Size, Src, (unsigned int *)&Size + 1, (unsigned __int8 **)&v21);
    v11 = v14;
    if ( v14 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v6 = v21;
        goto LABEL_20;
      }
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (unsigned int)v14);
      v6 = v21;
      goto LABEL_19;
    }
    v6 = v21;
    v10 = GmsapAddNewGMSAEntryToList(a1, a2, a3, a4, v21, a5);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v11 = 0;
      *((_DWORD *)*a5 + 24) = 1;
      goto LABEL_19;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 50;
      goto LABEL_8;
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 48;
LABEL_8:
      WPP_SF_D(v12[2], v13, &WPP_70b8577d707437755865c965214ce19a_Traceguids, (unsigned int)v10);
LABEL_19:
      v12 = WPP_GLOBAL_Control;
    }
  }
LABEL_20:
  v15 = Src;
  if ( Src )
  {
    v16 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v15++ = 0;
        --v16;
      }
      while ( v16 );
      v15 = Src;
    }
    (*((void (__fastcall **)(unsigned __int8 *))&xmmword_18000B580 + 1))(v15);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    v17 = HIDWORD(Size);
    v18 = v6;
    if ( HIDWORD(Size) )
    {
      do
      {
        *(_BYTE *)v18 = 0;
        v18 = (struct _tagPasswordData *)((char *)v18 + 1);
        --v17;
      }
      while ( v17 );
    }
    LocalFree(v6);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_D(v12[2], 51, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800043f0  push    rbp
0x1800043f2  push    rbx
0x1800043f3  push    rsi
0x1800043f4  push    rdi
0x1800043f5  push    r12
0x1800043f7  push    r13
0x1800043f9  push    r14
0x1800043fb  push    r15
0x1800043fd  mov     rbp, rsp
0x180004400  sub     rsp, 58h
0x180004404  xor     ebx, ebx
0x180004406  mov     r12, r9
0x180004409  mov     dword ptr [rbp+Size], ebx
0x18000440c  mov     edi, ebx
0x18000440e  mov     dword ptr [rbp+Size+4], ebx
0x180004411  mov     r14, r8
0x180004414  mov     [rbp+Src], rbx
0x180004418  mov     r15, rdx
0x18000441b  mov     [rbp+var_20], rbx
0x18000441f  mov     r13d, ecx
0x180004422  mov     rcx, cs:WPP_GLOBAL_Control
0x180004429  lea     rax, WPP_GLOBAL_Control
0x180004430  cmp     rcx, rax
0x180004433  jz      short loc_18000444E
0x180004435  test    byte ptr [rcx+1Ch], 8
0x180004439  jz      short loc_18000444E
0x18000443b  mov     rcx, [rcx+10h]
0x18000443f  lea     edx, [rbx+2Fh]
0x180004442  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004449  call    WPP_SF_
0x18000444e  mov     rsi, [rbp+arg_20]
0x180004452  lea     rax, [rbp+Src]
0x180004456  mov     [rsp+58h+var_38], rax
0x18000445b  lea     r9, [rbp+Size]
0x18000445f  mov     r8, r14
0x180004462  mov     rdx, r15
0x180004465  xor     ecx, ecx
0x180004467  mov     [rsi], rbx
0x18000446a  mov     rax, qword ptr cs:xmmword_18000B5B0
0x180004471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004476  mov     ebx, eax
0x180004478  test    eax, eax
0x18000447a  jns     short loc_1800044BA
0x18000447c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004483  lea     rsi, WPP_GLOBAL_Control
0x18000448a  cmp     rcx, rsi
0x18000448d  jz      loc_180004573
0x180004493  test    byte ptr [rcx+1Ch], 4
0x180004497  jz      loc_180004573
0x18000449d  mov     edx, 30h ; '0'
0x1800044a2  mov     rcx, [rcx+10h]
0x1800044a6  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800044ad  mov     r9d, eax
0x1800044b0  call    WPP_SF_D
0x1800044b5  jmp     loc_18000456C
0x1800044ba  mov     rdx, [rbp+Src]; Src
0x1800044be  lea     r9, [rbp+var_20]; unsigned __int8 **
0x1800044c2  mov     ecx, dword ptr [rbp+Size]; Size
0x1800044c5  lea     r8, [rbp+Size+4]; unsigned int *
0x1800044c9  call    ?GmsapParsePasswordData@@YAJKPEAEPEAKPEAPEAE@Z; GmsapParsePasswordData(ulong,uchar *,ulong *,uchar * *)
0x1800044ce  mov     ebx, eax
0x1800044d0  test    eax, eax
0x1800044d2  jns     short loc_180004511
0x1800044d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044db  lea     rsi, WPP_GLOBAL_Control
0x1800044e2  cmp     rcx, rsi
0x1800044e5  jz      short loc_18000450B
0x1800044e7  test    byte ptr [rcx+1Ch], 4
0x1800044eb  jz      short loc_18000450B
0x1800044ed  mov     rcx, [rcx+10h]
0x1800044f1  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800044f8  mov     edx, 31h ; '1'
0x1800044fd  mov     r9d, eax
0x180004500  call    WPP_SF_D
0x180004505  mov     rdi, [rbp+var_20]
0x180004509  jmp     short loc_18000456C
0x18000450b  mov     rdi, [rbp+var_20]
0x18000450f  jmp     short loc_180004573
0x180004511  mov     rdi, [rbp+var_20]
0x180004515  mov     r9, r12; unsigned __int16 *
0x180004518  mov     [rsp+58h+var_30], rsi; struct _tagGMsaListEntry **
0x18000451d  mov     r8, r14; unsigned __int16 *
0x180004520  mov     rdx, r15; unsigned __int16 *
0x180004523  mov     [rsp+58h+var_38], rdi; struct _tagPasswordData *
0x180004528  mov     ecx, r13d; int
0x18000452b  call    ?GmsapAddNewGMSAEntryToList@@YAJHPEBG00PEAU_tagPasswordData@@PEAPEAU_tagGMsaListEntry@@@Z; GmsapAddNewGMSAEntryToList(int,ushort const *,ushort const *,ushort const *,_tagPasswordData *,_tagGMsaListEntry * *)
0x180004530  mov     ebx, eax
0x180004532  test    eax, eax
0x180004534  jns     short loc_180004559
0x180004536  mov     rcx, cs:WPP_GLOBAL_Control
0x18000453d  lea     rsi, WPP_GLOBAL_Control
0x180004544  cmp     rcx, rsi
0x180004547  jz      short loc_180004573
0x180004549  test    byte ptr [rcx+1Ch], 4
0x18000454d  jz      short loc_180004573
0x18000454f  mov     edx, 32h ; '2'
0x180004554  jmp     loc_1800044A2
0x180004559  mov     rax, [rsi]
0x18000455c  xor     ebx, ebx
0x18000455e  lea     rsi, WPP_GLOBAL_Control
0x180004565  mov     dword ptr [rax+60h], 1
0x18000456c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004573  mov     rax, [rbp+Src]
0x180004577  test    rax, rax
0x18000457a  jz      short loc_1800045AA
0x18000457c  mov     ecx, dword ptr [rbp+Size]
0x18000457f  test    rcx, rcx
0x180004582  jz      short loc_180004594
0x180004584  mov     byte ptr [rax], 0
0x180004587  inc     rax
0x18000458a  sub     rcx, 1
0x18000458e  jnz     short loc_180004584
0x180004590  mov     rax, [rbp+Src]
0x180004594  mov     rcx, rax
0x180004597  mov     rax, qword ptr cs:xmmword_18000B580+8
0x18000459e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045aa  test    rdi, rdi
0x1800045ad  jz      short loc_1800045DC
0x1800045af  mov     eax, dword ptr [rbp+Size+4]
0x1800045b2  mov     rcx, rdi
0x1800045b5  test    rax, rax
0x1800045b8  jz      short loc_1800045C6
0x1800045ba  mov     byte ptr [rcx], 0
0x1800045bd  inc     rcx
0x1800045c0  sub     rax, 1
0x1800045c4  jnz     short loc_1800045BA
0x1800045c6  mov     rcx, rdi; hMem
0x1800045c9  call    cs:__imp_LocalFree
0x1800045d0  nop     dword ptr [rax+rax+00h]
0x1800045d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045dc  cmp     rcx, rsi
0x1800045df  jz      short loc_1800045FF
0x1800045e1  test    byte ptr [rcx+1Ch], 8
0x1800045e5  jz      short loc_1800045FF
0x1800045e7  mov     rcx, [rcx+10h]
0x1800045eb  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800045f2  mov     edx, 33h ; '3'
0x1800045f7  mov     r9d, ebx
0x1800045fa  call    WPP_SF_D
0x1800045ff  mov     eax, ebx
0x180004601  add     rsp, 58h
0x180004605  pop     r15
0x180004607  pop     r14
0x180004609  pop     r13
0x18000460b  pop     r12
0x18000460d  pop     rdi
0x18000460e  pop     rsi
0x18000460f  pop     rbx
0x180004610  pop     rbp
0x180004611  retn
```
