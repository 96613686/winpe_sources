# RtlpLoadInstallLanguageFallback

- ea: `0x1800bc688`
- end: `0x1800bc9de`
- name: `RtlpLoadInstallLanguageFallback`
- size: `854`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18000acb0`
- `0x18000c9a0`
- `0x18000ee60`
- `0x1801210e0`
- `0x18014dfb4`

## callees

- `0x18000b730`
- `0x18001861c`
- `0x18001b984`
- `0x1800bc688`
- `0x1800bccd0`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x1800bc6fb`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x1800bc77e`: `InstallLanguageFallback`

## pseudocode

```c
__int64 __fastcall RtlpLoadInstallLanguageFallback(__int64 a1, _WORD *a2, _WORD *a3)
{
  void *v5; // rax
  void *v6; // rsi
  size_t v7; // rax
  int v8; // ebx
  HANDLE v9; // rbx
  size_t v10; // rax
  _DWORD *Heap_0; // rdi
  int v12; // eax
  int v13; // r15d
  const wchar_t *i; // rdi
  __int16 *v15; // rcx
  size_t v17; // rax
  size_t v18; // rax
  __int16 v19; // ax
  HANDLE Handle; // [rsp+30h] [rbp-50h] BYREF
  __int128 v21; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[4]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v23; // [rsp+68h] [rbp-18h]
  int v24; // [rsp+C0h] [rbp+40h] BYREF
  int v25; // [rsp+D8h] [rbp+58h] BYREF

  Handle = 0;
  v24 = 0;
  v21 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v6 = 0;
    v8 = -1073741811;
    goto LABEL_24;
  }
  v5 = (void *)MuiRegAllocArray(a1, 172);
  v6 = v5;
  if ( !v5 )
  {
    v8 = -1073741801;
    goto LABEL_24;
  }
  memset_thunk_772440563353939046(v5, 0, 0x158u);
  *a2 = 0;
  *((_QWORD *)&v21 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language";
  *a3 = 0;
  *(_QWORD *)&v21 = 0;
  v7 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language");
  v22[0] = 48;
  v22[3] = 64;
  Handle = 0;
  v22[1] = 0;
  v23 = 0;
  if ( v7 >= 0xFFFE )
    LOWORD(v7) = -4;
  LOWORD(v21) = v7;
  WORD1(v21) = v7 + 2;
  v22[2] = &v21;
  v8 = NtOpenKey(&Handle, 131097, v22);
  if ( v8 >= 0 )
  {
    *(_QWORD *)&v21 = 0;
    *((_QWORD *)&v21 + 1) = L"InstallLanguageFallback";
    v9 = Handle;
    v10 = 2 * wcslen(L"InstallLanguageFallback");
    v25 = 0;
    if ( v10 >= 0xFFFE )
      LOWORD(v10) = -4;
    LOWORD(v21) = v10;
    WORD1(v21) = v10 + 2;
    Heap_0 = (_DWORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 356);
    if ( !Heap_0 )
    {
      v8 = -1073741670;
      goto LABEL_24;
    }
    v12 = NtQueryValueKey(v9, &v21, 2, Heap_0, 356, &v25);
    v8 = v12;
    if ( v12 >= 0 )
    {
      if ( Heap_0[2] > 0x158u )
        v8 = -2147483643;
      else
        memmove(v6, Heap_0 + 3, (unsigned int)Heap_0[2]);
    }
    else
    {
      v13 = 0;
      if ( v12 != -2147483643 )
      {
LABEL_17:
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
        if ( v8 >= 0 )
        {
          if ( v13 != 1 )
            goto LABEL_45;
          for ( i = (const wchar_t *)v6; *i; ++i )
          {
            v15 = (__int16 *)(i + 1);
            if ( *i == 44 )
            {
              *i++ = 0;
              v19 = *v15;
              if ( *v15 )
              {
                do
                {
                  if ( v19 != 32 )
                    break;
                  v19 = *++i;
                }
                while ( *i );
              }
              break;
            }
          }
          *(_QWORD *)&v21 = 0;
          *((_QWORD *)&v21 + 1) = v6;
          v17 = 2 * wcslen((const wchar_t *)v6);
          if ( v17 >= 0xFFFE )
            LOWORD(v17) = -4;
          LOWORD(v21) = v17;
          WORD1(v21) = v17 + 2;
          if ( (unsigned __int8)RtlCultureNameToLCID(&v21, &v24) )
          {
            *a2 = v24;
            if ( *i )
            {
              *(_QWORD *)&v21 = 0;
              *((_QWORD *)&v21 + 1) = i;
              v18 = 2 * wcslen(i);
              if ( v18 >= 0xFFFE )
                LOWORD(v18) = -4;
              LOWORD(v21) = v18;
              WORD1(v21) = v18 + 2;
              if ( (unsigned __int8)RtlCultureNameToLCID(&v21, &v24) )
              {
                *a3 = v24;
              }
              else
              {
                v8 = -1073741823;
                *a2 = 0;
              }
            }
          }
          else
          {
LABEL_45:
            v8 = -1073741823;
          }
        }
        goto LABEL_24;
      }
    }
    v13 = Heap_0[1];
    goto LABEL_17;
  }
LABEL_24:
  if ( Handle )
    NtClose(Handle);
  if ( v6 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800bc688  mov     [rsp-38h+arg_8], rbx
0x1800bc68d  push    rbp
0x1800bc68e  push    rsi
0x1800bc68f  push    rdi
0x1800bc690  push    r12
0x1800bc692  push    r13
0x1800bc694  push    r14
0x1800bc696  push    r15
0x1800bc698  mov     rbp, rsp
0x1800bc69b  sub     rsp, 80h
0x1800bc6a2  xor     r13d, r13d
0x1800bc6a5  xorps   xmm0, xmm0
0x1800bc6a8  mov     [rbp+Handle], r13
0x1800bc6ac  mov     r12, r8
0x1800bc6af  mov     [rbp+arg_0], r13d
0x1800bc6b3  mov     r14, rdx
0x1800bc6b6  movups  [rbp+var_48], xmm0
0x1800bc6ba  test    rcx, rcx
0x1800bc6bd  jz      loc_1800BC874
0x1800bc6c3  test    rdx, rdx
0x1800bc6c6  jz      loc_1800BC874
0x1800bc6cc  test    r8, r8
0x1800bc6cf  jz      loc_1800BC874
0x1800bc6d5  mov     edx, 0ACh
0x1800bc6da  call    _MuiRegAllocArray
0x1800bc6df  mov     rsi, rax
0x1800bc6e2  test    rax, rax
0x1800bc6e5  jz      loc_1800BC959
0x1800bc6eb  xor     edx, edx; Val
0x1800bc6ed  mov     r8d, 158h; Size
0x1800bc6f3  mov     rcx, rax; void *
0x1800bc6f6  call    memset$thunk$772440563353939046
0x1800bc6fb  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800bc702  mov     [r14], r13w
0x1800bc706  mov     qword ptr [rbp+var_48+8], rcx
0x1800bc70a  mov     [r12], r13w
0x1800bc70f  mov     qword ptr [rbp+var_48], r13
0x1800bc713  call    wcslen
0x1800bc718  add     rax, rax
0x1800bc71b  mov     [rbp+var_38], 30h ; '0'
0x1800bc723  mov     ecx, 0FFFCh
0x1800bc728  mov     [rbp+var_20], 40h ; '@'
0x1800bc730  xorps   xmm0, xmm0
0x1800bc733  mov     [rbp+Handle], r13
0x1800bc737  lea     r15d, [r13+2]
0x1800bc73b  mov     [rbp+var_30], r13
0x1800bc73f  lea     r8, [rbp+var_38]
0x1800bc743  mov     edx, 20019h
0x1800bc748  lea     edi, [rcx+2]
0x1800bc74b  cmp     rax, rdi
0x1800bc74e  movdqu  [rbp+var_18], xmm0
0x1800bc753  cmovnb  rax, rcx
0x1800bc757  lea     rcx, [rbp+Handle]
0x1800bc75b  mov     word ptr [rbp+var_48], ax
0x1800bc75f  add     ax, r15w
0x1800bc763  mov     word ptr [rbp+var_48+2], ax
0x1800bc767  lea     rax, [rbp+var_48]
0x1800bc76b  mov     [rbp+var_28], rax
0x1800bc76f  call    NtOpenKey
0x1800bc774  mov     ebx, eax
0x1800bc776  test    eax, eax
0x1800bc778  js      loc_1800BC87C
0x1800bc77e  lea     rcx, aInstalllanguag; "InstallLanguageFallback"
0x1800bc785  mov     qword ptr [rbp+var_48], r13
0x1800bc789  mov     qword ptr [rbp+var_48+8], rcx
0x1800bc78d  call    wcslen
0x1800bc792  mov     rbx, [rbp+Handle]
0x1800bc796  lea     ecx, [rdi-2]
0x1800bc799  add     rax, rax
0x1800bc79c  mov     [rbp+arg_18], r13d
0x1800bc7a0  cmp     rax, rdi
0x1800bc7a3  lea     edx, [r13+8]
0x1800bc7a7  mov     r8d, 164h
0x1800bc7ad  cmovnb  rax, rcx
0x1800bc7b1  mov     word ptr [rbp+var_48], ax
0x1800bc7b5  add     ax, r15w
0x1800bc7b9  mov     word ptr [rbp+var_48+2], ax
0x1800bc7bd  mov     rcx, gs:60h
0x1800bc7c6  mov     rcx, [rcx+30h]
0x1800bc7ca  call    RtlAllocateHeap_0
0x1800bc7cf  mov     rdi, rax
0x1800bc7d2  test    rax, rax
0x1800bc7d5  jz      loc_1800BC9CA
0x1800bc7db  lea     rax, [rbp+arg_18]
0x1800bc7df  mov     r9, rdi
0x1800bc7e2  mov     [rsp+80h+var_58], rax
0x1800bc7e7  lea     rdx, [rbp+var_48]
0x1800bc7eb  mov     r8d, r15d
0x1800bc7ee  mov     [rsp+80h+var_60], 164h
0x1800bc7f6  mov     rcx, rbx
0x1800bc7f9  call    NtQueryValueKey
0x1800bc7fe  mov     ebx, eax
0x1800bc800  test    eax, eax
0x1800bc802  jns     short loc_1800BC810
0x1800bc804  mov     r15d, r13d
0x1800bc807  cmp     eax, 80000005h
0x1800bc80c  jz      short loc_1800BC82D
0x1800bc80e  jmp     short loc_1800BC831
0x1800bc810  cmp     dword ptr [rdi+8], 158h
0x1800bc817  ja      loc_1800BC9C0
0x1800bc81d  mov     r8d, [rdi+8]; Size
0x1800bc821  lea     rdx, [rdi+0Ch]; Src
0x1800bc825  mov     rcx, rsi; void *
0x1800bc828  call    memmove
0x1800bc82d  mov     r15d, [rdi+4]
0x1800bc831  mov     rcx, gs:60h
0x1800bc83a  mov     r8, rdi
0x1800bc83d  xor     edx, edx
0x1800bc83f  mov     rcx, [rcx+30h]
0x1800bc843  call    RtlFreeHeap_0
0x1800bc848  test    ebx, ebx
0x1800bc84a  js      short loc_1800BC87C
0x1800bc84c  cmp     r15d, 1
0x1800bc850  jnz     loc_1800BC9D4
0x1800bc856  mov     rdi, rsi
0x1800bc859  movzx   eax, word ptr [rdi]
0x1800bc85c  test    ax, ax
0x1800bc85f  jz      short loc_1800BC8B1
0x1800bc861  lea     rcx, [rdi+2]
0x1800bc865  cmp     ax, 2Ch ; ','
0x1800bc869  jz      loc_1800BC963
0x1800bc86f  mov     rdi, rcx
0x1800bc872  jmp     short loc_1800BC859
0x1800bc874  mov     rsi, r13
0x1800bc877  mov     ebx, 0C000000Dh
0x1800bc87c  mov     rcx, [rbp+Handle]; Handle
0x1800bc880  test    rcx, rcx
0x1800bc883  jz      short loc_1800BC88A
0x1800bc885  call    NtClose
0x1800bc88a  test    rsi, rsi
0x1800bc88d  jnz     loc_1800BC9A4
0x1800bc893  mov     eax, ebx
0x1800bc895  mov     rbx, [rsp+80h+arg_8]
0x1800bc89d  add     rsp, 80h
0x1800bc8a4  pop     r15
0x1800bc8a6  pop     r14
0x1800bc8a8  pop     r13
0x1800bc8aa  pop     r12
0x1800bc8ac  pop     rdi
0x1800bc8ad  pop     rsi
0x1800bc8ae  pop     rbp
0x1800bc8af  retn
0x1800bc8b1  mov     r15d, 2
0x1800bc8b7  mov     rcx, rsi; String
0x1800bc8ba  mov     qword ptr [rbp+var_48], r13
0x1800bc8be  mov     qword ptr [rbp+var_48+8], rsi
0x1800bc8c2  call    wcslen
0x1800bc8c7  add     rax, rax
0x1800bc8ca  lea     rdx, [rbp+arg_0]
0x1800bc8ce  cmp     rax, 0FFFEh
0x1800bc8d4  mov     ecx, 0FFFCh
0x1800bc8d9  cmovnb  rax, rcx
0x1800bc8dd  lea     rcx, [rbp+var_48]
0x1800bc8e1  mov     word ptr [rbp+var_48], ax
0x1800bc8e5  add     ax, r15w
0x1800bc8e9  mov     word ptr [rbp+var_48+2], ax
0x1800bc8ed  call    RtlCultureNameToLCID
0x1800bc8f2  test    al, al
0x1800bc8f4  jz      loc_1800BC9D4
0x1800bc8fa  movzx   eax, word ptr [rbp+arg_0]
0x1800bc8fe  mov     [r14], ax
0x1800bc902  cmp     [rdi], r13w
0x1800bc906  jz      loc_1800BC87C
0x1800bc90c  mov     rcx, rdi; String
0x1800bc90f  mov     qword ptr [rbp+var_48], r13
0x1800bc913  mov     qword ptr [rbp+var_48+8], rdi
0x1800bc917  call    wcslen
0x1800bc91c  add     rax, rax
0x1800bc91f  lea     rdx, [rbp+arg_0]
0x1800bc923  cmp     rax, 0FFFEh
0x1800bc929  mov     ecx, 0FFFCh
0x1800bc92e  cmovnb  rax, rcx
0x1800bc932  lea     rcx, [rbp+var_48]
0x1800bc936  mov     word ptr [rbp+var_48], ax
0x1800bc93a  add     ax, r15w
0x1800bc93e  mov     word ptr [rbp+var_48+2], ax
0x1800bc942  call    RtlCultureNameToLCID
0x1800bc947  test    al, al
0x1800bc949  jnz     short loc_1800BC996
0x1800bc94b  mov     ebx, 0C0000001h
0x1800bc950  mov     [r14], r13w
0x1800bc954  jmp     loc_1800BC87C
0x1800bc959  mov     ebx, 0C0000017h
0x1800bc95e  jmp     loc_1800BC87C
0x1800bc963  mov     [rdi], r13w
0x1800bc967  mov     rdi, rcx
0x1800bc96a  movzx   eax, word ptr [rcx]
0x1800bc96d  test    ax, ax
0x1800bc970  jz      loc_1800BC8B1
0x1800bc976  mov     r15d, 2
0x1800bc97c  cmp     ax, 20h ; ' '
0x1800bc980  jnz     loc_1800BC8B7
0x1800bc986  add     rdi, r15
0x1800bc989  movzx   eax, word ptr [rdi]
0x1800bc98c  test    ax, ax
0x1800bc98f  jnz     short loc_1800BC97C
0x1800bc991  jmp     loc_1800BC8B7
0x1800bc996  movzx   eax, word ptr [rbp+arg_0]
0x1800bc99a  mov     [r12], ax
0x1800bc99f  jmp     loc_1800BC87C
0x1800bc9a4  mov     rcx, gs:60h
0x1800bc9ad  mov     r8, rsi
0x1800bc9b0  xor     edx, edx
0x1800bc9b2  mov     rcx, [rcx+30h]
0x1800bc9b6  call    RtlFreeHeap_0
0x1800bc9bb  jmp     loc_1800BC893
0x1800bc9c0  mov     ebx, 80000005h
0x1800bc9c5  jmp     loc_1800BC82D
0x1800bc9ca  mov     ebx, 0C000009Ah
0x1800bc9cf  jmp     loc_1800BC87C
0x1800bc9d4  mov     ebx, 0C0000001h
0x1800bc9d9  jmp     loc_1800BC87C
```
