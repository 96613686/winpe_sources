# EtwpGetRegDwordValue

- ea: `0x1800353f0`
- end: `0x1800355d1`
- name: `EtwpGetRegDwordValue`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035a70`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800353f0`
- `0x180100a8c`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`

## string_xrefs

- `0x18003545d`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall EtwpGetRegDwordValue(__int64 a1, __int64 a2, _DWORD *a3)
{
  wchar_t *Heap_0; // rsi
  size_t v5; // rax
  int v6; // ebx
  size_t v7; // rdx
  __int64 v8; // rdi
  size_t *v9; // r8
  const wchar_t *v10; // r9
  size_t v12; // rax
  size_t v13; // [rsp+20h] [rbp-60h]
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  __int128 v15; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v16[48]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF
  int v18; // [rsp+B8h] [rbp+38h] BYREF
  int v19; // [rsp+BCh] [rbp+3Ch]

  v19 = HIDWORD(a2);
  v18 = 0;
  Handle = (HANDLE)-1LL;
  memset(v16, 0, 44);
  v14 = 0;
  Heap_0 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 4096);
  if ( !Heap_0 )
    return 3221225495LL;
  *(_QWORD *)&v14 = 0;
  *((_QWORD *)&v14 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
  v5 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control");
  *(_OWORD *)v16 = 0x30u;
  *(_QWORD *)&v16[24] = 64;
  if ( v5 >= 0xFFFE )
    LOWORD(v5) = -4;
  LOWORD(v14) = v5;
  WORD1(v14) = v5 + 2;
  *(_QWORD *)&v16[16] = &v14;
  *(_OWORD *)&v16[32] = 0;
  v6 = NtOpenKey(&Handle, 131097, v16);
  if ( v6 >= 0 )
  {
    v8 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 16);
    if ( v8 )
    {
      v15 = 0;
      StringCopyWorkerW(Heap_0, v7, v9, v10, v13);
      *(_QWORD *)&v15 = 0;
      *((_QWORD *)&v15 + 1) = Heap_0;
      v12 = 2 * wcslen(Heap_0);
      if ( v12 >= 0xFFFE )
        LOWORD(v12) = -4;
      LOWORD(v15) = v12;
      WORD1(v15) = v12 + 2;
      v6 = NtQueryValueKey(Handle, &v15, 2, v8, 16, &v18);
      if ( v6 >= 0 )
        *a3 = *(_DWORD *)(v8 + 12);
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    else
    {
      v6 = -1073741801;
    }
    NtClose(Handle);
  }
  RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800353f0  mov     [rsp-28h+arg_10], rbx
0x1800353f5  mov     [rsp-28h+arg_8], rdx
0x1800353fa  mov     [rsp-28h+Handle], rcx
0x1800353ff  push    rbp
0x180035400  push    rsi
0x180035401  push    rdi
0x180035402  push    r12
0x180035404  push    r14
0x180035406  mov     rbp, rsp
0x180035409  sub     rsp, 80h
0x180035410  xorps   xmm0, xmm0
0x180035413  mov     dword ptr [rbp+arg_8], 0
0x18003541a  movups  [rbp+var_20], xmm0
0x18003541e  mov     [rbp+Handle], 0FFFFFFFFFFFFFFFFh
0x180035426  mov     r14, r8
0x180035429  movups  [rbp+var_20+0Ch], xmm0
0x18003542d  xor     eax, eax
0x18003542f  xor     edx, edx
0x180035431  movups  [rbp+var_30], xmm0
0x180035435  mov     r8d, 1000h
0x18003543b  movups  [rbp+var_50], xmm0
0x18003543f  mov     rcx, gs:60h
0x180035448  mov     rcx, [rcx+30h]
0x18003544c  call    RtlAllocateHeap_0
0x180035451  mov     rsi, rax
0x180035454  test    rax, rax
0x180035457  jz      loc_1800355BF
0x18003545d  lea     rcx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x180035464  mov     qword ptr [rbp+var_50], 0
0x18003546c  mov     qword ptr [rbp+var_50+8], rcx
0x180035470  call    wcslen
0x180035475  add     rax, rax
0x180035478  mov     qword ptr [rbp+var_30], 30h ; '0'
0x180035480  cmp     rax, 0FFFEh
0x180035486  mov     qword ptr [rbp+var_20+8], 40h ; '@'
0x18003548e  mov     ecx, 0FFFCh
0x180035493  mov     qword ptr [rbp+var_30+8], 0
0x18003549b  cmovnb  rax, rcx
0x18003549f  lea     r8, [rbp+var_30]
0x1800354a3  mov     word ptr [rbp+var_50], ax
0x1800354a7  lea     rcx, [rbp+Handle]
0x1800354ab  xorps   xmm0, xmm0
0x1800354ae  mov     r12d, 2
0x1800354b4  add     ax, r12w
0x1800354b8  mov     edx, 20019h
0x1800354bd  mov     word ptr [rbp+var_50+2], ax
0x1800354c1  lea     rax, [rbp+var_50]
0x1800354c5  mov     qword ptr [rbp+var_20], rax
0x1800354c9  movdqu  [rbp+var_10], xmm0
0x1800354ce  call    NtOpenKey
0x1800354d3  mov     ebx, eax
0x1800354d5  test    eax, eax
0x1800354d7  js      short loc_18003550B
0x1800354d9  mov     rcx, gs:60h
0x1800354e2  lea     ebx, [r12+0Eh]
0x1800354e7  mov     r8d, ebx
0x1800354ea  xor     edx, edx
0x1800354ec  mov     rcx, [rcx+30h]
0x1800354f0  call    RtlAllocateHeap_0
0x1800354f5  mov     rdi, rax
0x1800354f8  test    rax, rax
0x1800354fb  jnz     short loc_18003553C
0x1800354fd  mov     ebx, 0C0000017h
0x180035502  mov     rcx, [rbp+Handle]; Handle
0x180035506  call    NtClose
0x18003550b  mov     rcx, gs:60h
0x180035514  mov     r8, rsi
0x180035517  xor     edx, edx
0x180035519  mov     rcx, [rcx+30h]
0x18003551d  call    RtlFreeHeap_0
0x180035522  mov     eax, ebx
0x180035524  mov     rbx, [rsp+80h+arg_10]
0x18003552c  add     rsp, 80h
0x180035533  pop     r14
0x180035535  pop     r12
0x180035537  pop     rdi
0x180035538  pop     rsi
0x180035539  pop     rbp
0x18003553a  retn
0x18003553c  xorps   xmm0, xmm0
0x18003553f  mov     rcx, rsi; pszDest
0x180035542  movups  [rbp+var_40], xmm0
0x180035546  call    StringCopyWorkerW
0x18003554b  mov     rcx, rsi; String
0x18003554e  mov     qword ptr [rbp+var_40], 0
0x180035556  mov     qword ptr [rbp+var_40+8], rsi
0x18003555a  call    wcslen
0x18003555f  add     rax, rax
0x180035562  lea     rdx, [rbp+var_40]
0x180035566  cmp     rax, 0FFFEh
0x18003556c  mov     ecx, 0FFFCh
0x180035571  mov     r9, rdi
0x180035574  mov     r8d, r12d
0x180035577  cmovnb  rax, rcx
0x18003557b  mov     rcx, [rbp+Handle]
0x18003557f  mov     word ptr [rbp+var_40], ax
0x180035583  add     ax, r12w
0x180035587  mov     word ptr [rbp+var_40+2], ax
0x18003558b  lea     rax, [rbp+arg_8]
0x18003558f  mov     [rsp+80h+var_58], rax
0x180035594  mov     dword ptr [rsp+80h+var_60], ebx
0x180035598  call    NtQueryValueKey
0x18003559d  mov     ebx, eax
0x18003559f  test    eax, eax
0x1800355a1  jns     short loc_1800355C9
0x1800355a3  mov     rcx, gs:60h
0x1800355ac  mov     r8, rdi
0x1800355af  xor     edx, edx
0x1800355b1  mov     rcx, [rcx+30h]
0x1800355b5  call    RtlFreeHeap_0
0x1800355ba  jmp     loc_180035502
0x1800355bf  mov     eax, 0C0000017h
0x1800355c4  jmp     loc_180035524
0x1800355c9  mov     eax, [rdi+0Ch]
0x1800355cc  mov     [r14], eax
0x1800355cf  jmp     short loc_1800355A3
```
