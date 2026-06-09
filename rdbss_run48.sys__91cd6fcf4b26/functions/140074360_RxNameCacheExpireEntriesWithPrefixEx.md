# RxNameCacheExpireEntriesWithPrefixEx

- ea: `0x140074360`
- end: `0x1400745ee`
- name: `RxNameCacheExpireEntriesWithPrefixEx`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140074340`

## callees

- `0x140014e40`
- `0x14001e83c`
- `0x140025d00`
- `0x140074360`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140074418`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140074418`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400743d0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400743d0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140074444`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140074444`

## pseudocode

```c
__int64 __fastcall RxNameCacheExpireEntriesWithPrefixEx(__int64 a1, const UNICODE_STRING *a2, char a3)
{
  unsigned __int64 v5; // r12
  __int64 *v6; // rbx
  __int64 *v7; // rbp
  void (__fastcall *v9)(_QWORD, __int64); // rax
  __int64 *v10; // rax
  __int64 **v11; // rcx
  __int64 **v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  unsigned __int64 Length; // rdx
  bool v18; // [rsp+70h] [rbp+8h]
  unsigned __int64 v19; // [rsp+78h] [rbp+10h]

  v18 = 0;
  v5 = MEMORY[0xFFFFF78000000008];
  v19 = MEMORY[0xFFFFF78000000008];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Zq(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      (unsigned int)&WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids,
      (_DWORD)a2,
      a1);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 104));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 120));
  if ( a2->Length >= 2u )
    v18 = a2->Buffer[((unsigned __int64)a2->Length >> 1) - 1] == 92;
  ExAcquirePushLockExclusiveEx(a1 + 48, 0);
  v6 = *(__int64 **)(a1 + 56);
  if ( v6 != (__int64 *)(a1 + 56) )
  {
    do
    {
      v7 = (__int64 *)*v6;
      if ( *((_WORD *)v6 - 32) != 0xEBAA )
      {
        if ( !a2->Length || v5 >= *(v6 - 1) )
          goto LABEL_13;
        if ( *((_WORD *)v6 + 8) >= a2->Length
          && RtlPrefixUnicodeString(a2, (PCUNICODE_STRING)v6 + 1, *((_BYTE *)v6 + 64)) )
        {
          if ( !a3 || v18 )
          {
            v5 = v19;
LABEL_13:
            v9 = *(void (__fastcall **)(_QWORD, __int64))(a1 + 136);
            if ( v9 )
            {
              v9(*(_QWORD *)(a1 + 144), (__int64)(v6 - 8));
              *(v6 - 3) = 0;
            }
            v10 = (__int64 *)*v6;
            if ( *(__int64 **)(*v6 + 8) != v6 )
              goto LABEL_18;
            v11 = (__int64 **)v6[1];
            if ( *v11 != v6 )
              goto LABEL_18;
            *v11 = v10;
            v10[1] = (__int64)v11;
            v12 = (__int64 **)(a1 + 72);
            v13 = *(_QWORD *)(a1 + 72);
            if ( *(_QWORD *)(v13 + 8) != a1 + 72
              || (v6[1] = (__int64)v12,
                  *v6 = v13,
                  *(_QWORD *)(v13 + 8) = v6,
                  *v12 = v6,
                  v14 = v6 + 4,
                  v15 = v6[4],
                  *(__int64 **)(v15 + 8) != v6 + 4)
              || (v16 = (_QWORD *)v6[5], (_QWORD *)*v16 != v14) )
            {
LABEL_18:
              __fastfail(3u);
            }
            *v16 = v15;
            *(_QWORD *)(v15 + 8) = v16;
            v6[5] = (__int64)v14;
            *v14 = v14;
            _InterlockedDecrement((volatile signed __int32 *)(a1 + 100));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, v6 + 2);
            }
            goto LABEL_11;
          }
          Length = a2->Length;
          v5 = v19;
          if ( *((unsigned __int16 *)v6 + 8) < Length + 2 || *(_WORD *)(v6[3] + 2 * (Length >> 1)) == 92 )
            goto LABEL_13;
        }
        else
        {
          v5 = v19;
        }
      }
LABEL_11:
      v6 = v7;
    }
    while ( v7 != (__int64 *)(a1 + 56) );
  }
  return ExReleasePushLockExclusiveEx(a1 + 48, 0);
}

```

## disassembly

```asm
0x140074360  mov     [rsp+arg_10], r8b
0x140074365  push    rbx
0x140074366  push    rsi
0x140074367  push    r12
0x140074369  push    r13
0x14007436b  push    r14
0x14007436d  push    r15
0x14007436f  sub     rsp, 38h
0x140074373  mov     r12, 0FFFFF78000000008h
0x14007437d  mov     [rsp+68h+arg_0], 0
0x140074382  mov     r15, rdx
0x140074385  mov     rsi, rcx
0x140074388  mov     r12, [r12]
0x14007438c  mov     [rsp+68h+arg_8], r12
0x140074391  mov     rcx, cs:WPP_GLOBAL_Control
0x140074398  lea     rax, WPP_GLOBAL_Control
0x14007439f  cmp     rcx, rax
0x1400743a2  jnz     loc_1400744AA
0x1400743a8  lock inc dword ptr [rsi+68h]
0x1400743ac  lock inc dword ptr [rsi+78h]
0x1400743b0  movzx   eax, word ptr [r15]
0x1400743b4  cmp     eax, 2
0x1400743b7  jnb     loc_1400744E3
0x1400743bd  mov     [rsp+68h+arg_18], rbp
0x1400743c5  lea     rcx, [rsi+30h]
0x1400743c9  xor     edx, edx
0x1400743cb  mov     [rsp+68h+var_38], rdi
0x1400743d0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400743d7  nop     dword ptr [rax+rax+00h]
0x1400743dc  mov     rbx, [rsi+38h]
0x1400743e0  lea     r14, [rsi+38h]
0x1400743e4  cmp     rbx, r14
0x1400743e7  jz      short loc_14007443E
0x1400743e9  mov     eax, 0EBAAh
0x1400743ee  mov     rbp, [rbx]
0x1400743f1  cmp     [rbx-40h], ax
0x1400743f5  jz      short loc_140074436
0x1400743f7  movzx   eax, word ptr [r15]
0x1400743fb  test    ax, ax
0x1400743fe  jz      short loc_14007446D
0x140074400  cmp     r12, [rbx-8]
0x140074404  jnb     short loc_14007446D
0x140074406  cmp     [rbx+10h], ax
0x14007440a  jb      short loc_14007442C
0x14007440c  movzx   r8d, byte ptr [rbx+40h]; CaseInSensitive
0x140074411  lea     rdx, [rbx+10h]; String2
0x140074415  mov     rcx, r15; String1
0x140074418  call    cs:__imp_RtlPrefixUnicodeString
0x14007441f  nop     dword ptr [rax+rax+00h]
0x140074424  test    al, al
0x140074426  jnz     loc_140074587
0x14007442c  mov     r12, [rsp+68h+arg_8]
0x140074431  mov     eax, 0EBAAh
0x140074436  mov     rbx, rbp
0x140074439  cmp     rbp, r14
0x14007443c  jnz     short loc_1400743EE
0x14007443e  xor     edx, edx
0x140074440  lea     rcx, [rsi+30h]
0x140074444  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14007444b  nop     dword ptr [rax+rax+00h]
0x140074450  mov     rdi, [rsp+68h+var_38]
0x140074455  mov     rbp, [rsp+68h+arg_18]
0x14007445d  add     rsp, 38h
0x140074461  pop     r15
0x140074463  pop     r14
0x140074465  pop     r13
0x140074467  pop     r12
0x140074469  pop     rsi
0x14007446a  pop     rbx
0x14007446b  retn
0x14007446d  mov     rax, [rsi+88h]
0x140074474  test    rax, rax
0x140074477  jnz     loc_1400745D1
0x14007447d  mov     rax, [rbx]
0x140074480  cmp     [rax+8], rbx
0x140074484  jnz     short loc_1400744A3
0x140074486  mov     rcx, [rbx+8]
0x14007448a  cmp     [rcx], rbx
0x14007448d  jnz     short loc_1400744A3
0x14007448f  mov     [rcx], rax
0x140074492  mov     [rax+8], rcx
0x140074496  lea     rax, [rsi+48h]
0x14007449a  mov     rcx, [rax]
0x14007449d  cmp     [rcx+8], rax
0x1400744a1  jz      short loc_140074501
0x1400744a3  mov     ecx, 3
0x1400744a8  int     29h; Win8: RtlFailFast(ecx)
0x1400744aa  test    dword ptr [rcx+2Ch], 800h
0x1400744b1  jz      loc_1400743A8
0x1400744b7  cmp     byte ptr [rcx+29h], 4
0x1400744bb  jb      loc_1400743A8
0x1400744c1  mov     rcx, [rcx+18h]
0x1400744c5  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x1400744cc  mov     edx, 17h
0x1400744d1  mov     [rsp+68h+var_48], rsi
0x1400744d6  mov     r9, r15
0x1400744d9  call    WPP_SF_Zq
0x1400744de  jmp     loc_1400743A8
0x1400744e3  mov     rcx, rax
0x1400744e6  mov     edx, 5Ch ; '\'
0x1400744eb  mov     rax, [r15+8]
0x1400744ef  shr     rcx, 1
0x1400744f2  cmp     dx, [rax+rcx*2-2]
0x1400744f7  setz    [rsp+68h+arg_0]
0x1400744fc  jmp     loc_1400743BD
0x140074501  mov     [rbx+8], rax
0x140074505  mov     [rbx], rcx
0x140074508  mov     [rcx+8], rbx
0x14007450c  mov     [rax], rbx
0x14007450f  lea     rax, [rbx+20h]
0x140074513  mov     rdx, [rax]
0x140074516  cmp     [rdx+8], rax
0x14007451a  jnz     short loc_1400744A3
0x14007451c  mov     rcx, [rbx+28h]
0x140074520  cmp     [rcx], rax
0x140074523  jnz     loc_1400744A3
0x140074529  mov     [rcx], rdx
0x14007452c  mov     [rdx+8], rcx
0x140074530  mov     [rbx+28h], rax
0x140074534  mov     [rax], rax
0x140074537  lock dec dword ptr [rsi+64h]
0x14007453b  mov     rcx, cs:WPP_GLOBAL_Control
0x140074542  lea     rax, WPP_GLOBAL_Control
0x140074549  cmp     rcx, rax
0x14007454c  jz      loc_140074431
0x140074552  test    dword ptr [rcx+2Ch], 800h
0x140074559  jz      loc_140074431
0x14007455f  cmp     byte ptr [rcx+29h], 4
0x140074563  jb      loc_140074431
0x140074569  mov     rcx, [rcx+18h]
0x14007456d  lea     r9, [rbx+10h]
0x140074571  mov     edx, 18h
0x140074576  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14007457d  call    WPP_SF_Z
0x140074582  jmp     loc_140074431
0x140074587  cmp     [rsp+68h+arg_10], 0
0x14007458f  jz      loc_14007F8F0
0x140074595  cmp     [rsp+68h+arg_0], 0
0x14007459a  jnz     loc_14007F8F0
0x1400745a0  movzx   edx, word ptr [r15]
0x1400745a4  movzx   eax, word ptr [rbx+10h]
0x1400745a8  mov     r12, [rsp+68h+arg_8]
0x1400745ad  lea     rcx, [rdx+2]
0x1400745b1  cmp     rax, rcx
0x1400745b4  jb      loc_14007446D
0x1400745ba  mov     rax, [rbx+18h]
0x1400745be  shr     rdx, 1
0x1400745c1  cmp     word ptr [rax+rdx*2], 5Ch ; '\'
0x1400745c6  jnz     loc_140074431
0x1400745cc  jmp     loc_14007446D
0x1400745d1  mov     rcx, [rsi+90h]
0x1400745d8  lea     rdx, [rbx-40h]
0x1400745dc  call    _guard_dispatch_icall
0x1400745e1  mov     qword ptr [rbx-18h], 0
0x1400745e9  jmp     loc_14007447D
0x14007f8f0  mov     r12, [rsp+68h+arg_8]
0x14007f8f5  jmp     loc_14007446D
```
