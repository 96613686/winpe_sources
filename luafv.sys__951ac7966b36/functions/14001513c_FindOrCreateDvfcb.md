# FindOrCreateDvfcb

- ea: `0x14001513c`
- end: `0x14001537f`
- name: `FindOrCreateDvfcb`
- size: `579`
- prototype: `__int64 *__fastcall(PCUNICODE_STRING String2, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400157d4`

## callees

- `0x140006080`
- `0x140006380`
- `0x14001513c`
- `0x14001b6a0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400151a6`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140015201`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400151a6`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140015201`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015280`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015280`
- `FLTMGR!FltInitializePushLock` at `0x140015323`
- `FLTMGR!FltInitializePushLock` at `0x140015323`
- `FLTMGR!FltReleasePushLockEx` at `0x14001535e`
- `FLTMGR!FltReleasePushLockEx` at `0x14001535e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001524a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001524a`

## pseudocode

```c
__int64 *__fastcall FindOrCreateDvfcb(PCUNICODE_STRING String2, int *a2)
{
  PWSTR Buffer; // rbx
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rsi
  WCHAR *v8; // r12
  __int64 v9; // rdi
  int v10; // r15d
  __int64 v11; // rax
  __int128 v12; // rt0
  int v13; // eax
  int v14; // edi
  WCHAR *v15; // rsi
  unsigned int v16; // eax
  int v17; // ebp
  __int64 *v18; // rdi
  __int64 v19; // r8
  __int64 *i; // rsi
  __int64 *v21; // rbx
  unsigned int v22; // esi
  __int64 *Pool; // rax
  USHORT Length; // ax
  __int64 v25; // rdx

  Buffer = String2->Buffer;
  v5 = String2->Length >> 1;
  v6 = String2->Length >> 3;
  if ( (_DWORD)v6 )
  {
    v7 = 0;
    v8 = &Buffer[4 * v6];
    do
    {
      v9 = *(_QWORD *)Buffer;
      if ( (*(_QWORD *)Buffer & 0xFF80FF80FF80FF80uLL) != 0 )
      {
        v10 = 4;
        do
        {
          v11 = (unsigned __int16)v9;
          if ( (unsigned __int16)v9 >= 0x61u )
          {
            if ( (unsigned __int16)v9 <= 0x7Au )
              v11 = (unsigned int)(unsigned __int16)v9 - 32;
            else
              v11 = RtlUpcaseUnicodeChar(v9);
          }
          *(_QWORD *)&v12 = v9;
          *((_QWORD *)&v12 + 1) = v11;
          v9 = v12 >> 16;
          --v10;
        }
        while ( v10 );
      }
      else
      {
        v9 &= 0xFFDFFFDFFFDFFFDFuLL;
      }
      Buffer += 4;
      v7 = v9 ^ __ROL8__(v7, 1);
    }
    while ( Buffer < v8 );
    v5 &= 3u;
    v13 = v7 ^ __ROR8__(v7, 33);
    v14 = v13 ^ __ROR4__(v13, 17);
  }
  else
  {
    v14 = 0;
  }
  v15 = &Buffer[v5];
  while ( Buffer < v15 )
  {
    v16 = *Buffer;
    if ( v16 >= 0x61 )
    {
      if ( v16 <= 0x7A )
        v16 -= 32;
      else
        v16 = RtlUpcaseUnicodeChar(v16);
    }
    v14 = v16 ^ __ROL4__(v14, 1);
    ++Buffer;
  }
  v17 = v14 ^ __ROR4__(v14, 8);
  *a2 = v17;
  v18 = &LuafvDvfcbHashTable[3 * (v17 & 0xF)];
  FltAcquirePushLockExclusiveEx(v18 + 2, 0);
  for ( i = (__int64 *)*v18; i != v18; i = (__int64 *)*i )
  {
    v21 = i - 1;
    if ( *((_DWORD *)i + 12) == v17
      && *((_WORD *)v21 + 20) == String2->Length
      && RtlEqualUnicodeString((PCUNICODE_STRING)(v21 + 5), String2, 1u) )
    {
      _InterlockedAdd((volatile signed __int32 *)v21, 1u);
      goto LABEL_32;
    }
  }
  LOBYTE(v19) = 7;
  v22 = String2->Length + 122;
  Pool = (__int64 *)LuafvAllocatePool(1, v22, v19);
  v21 = Pool;
  if ( Pool )
  {
    _InterlockedAdd(&LuafvActiveDvfcbCount, 1u);
    memset(Pool, 0, v22);
    *(_DWORD *)v21 = 1;
    v21[4] = (__int64)(v21 + 3);
    v21[3] = (__int64)(v21 + 3);
    *((_WORD *)v21 + 20) = String2->Length;
    Length = String2->Length;
    v21[6] = (__int64)(v21 + 15);
    *((_WORD *)v21 + 21) = Length + 2;
    memmove(v21 + 15, String2->Buffer, String2->Length);
    *(_WORD *)(v21[6] + 2 * ((unsigned __int64)String2->Length >> 1)) = 0;
    *((_DWORD *)v21 + 14) = v17;
    FltInitializePushLock((PULONG_PTR)v21 + 8);
    v21[14] = 0;
    v25 = *v18;
    if ( *(__int64 **)(*v18 + 8) != v18 )
      __fastfail(3u);
    v21[1] = v25;
    v21[2] = (__int64)v18;
    *(_QWORD *)(v25 + 8) = v21 + 1;
    *v18 = (__int64)(v21 + 1);
  }
LABEL_32:
  FltReleasePushLockEx(v18 + 2, 0);
  return v21;
}

```

## disassembly

```asm
0x14001513c  push    rbx
0x14001513e  push    rbp
0x14001513f  push    rsi
0x140015140  push    rdi
0x140015141  push    r12
0x140015143  push    r13
0x140015145  push    r14
0x140015147  push    r15
0x140015149  sub     rsp, 28h
0x14001514d  movzx   ebp, word ptr [rcx]
0x140015150  mov     r13, rdx
0x140015153  mov     rbx, [rcx+8]
0x140015157  mov     r14, rcx
0x14001515a  shr     ebp, 1
0x14001515c  mov     eax, ebp
0x14001515e  shr     eax, 2
0x140015161  test    eax, eax
0x140015163  jz      loc_1400151E9
0x140015169  xor     esi, esi
0x14001516b  lea     r12, [rbx+rax*8]
0x14001516f  mov     rdi, [rbx]
0x140015172  mov     rax, 0FF80FF80FF80FF80h
0x14001517c  test    rax, rdi
0x14001517f  jnz     short loc_140015190
0x140015181  mov     rax, 0FFDFFFDFFFDFFFDFh
0x14001518b  and     rdi, rax
0x14001518e  jmp     short loc_1400151C5
0x140015190  mov     r15d, 4
0x140015196  movzx   eax, di
0x140015199  cmp     eax, 61h ; 'a'
0x14001519c  jb      short loc_1400151BA
0x14001519e  cmp     eax, 7Ah ; 'z'
0x1400151a1  jbe     short loc_1400151B7
0x1400151a3  movzx   ecx, ax; SourceCharacter
0x1400151a6  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400151ad  nop     dword ptr [rax+rax+00h]
0x1400151b2  movzx   eax, ax
0x1400151b5  jmp     short loc_1400151BA
0x1400151b7  add     eax, 0FFFFFFE0h
0x1400151ba  shrd    rdi, rax, 10h
0x1400151bf  add     r15d, 0FFFFFFFFh
0x1400151c3  jnz     short loc_140015196
0x1400151c5  rol     rsi, 1
0x1400151c8  add     rbx, 8
0x1400151cc  xor     rsi, rdi
0x1400151cf  cmp     rbx, r12
0x1400151d2  jb      short loc_14001516F
0x1400151d4  mov     rax, rsi
0x1400151d7  and     ebp, 3
0x1400151da  ror     rax, 21h
0x1400151de  xor     eax, esi
0x1400151e0  mov     edi, eax
0x1400151e2  ror     edi, 11h
0x1400151e5  xor     edi, eax
0x1400151e7  jmp     short loc_1400151EB
0x1400151e9  xor     edi, edi
0x1400151eb  lea     rsi, [rbx+rbp*2]
0x1400151ef  jmp     short loc_14001521D
0x1400151f1  movzx   eax, word ptr [rbx]
0x1400151f4  cmp     eax, 61h ; 'a'
0x1400151f7  jb      short loc_140015215
0x1400151f9  cmp     eax, 7Ah ; 'z'
0x1400151fc  jbe     short loc_140015212
0x1400151fe  movzx   ecx, ax; SourceCharacter
0x140015201  call    cs:__imp_RtlUpcaseUnicodeChar
0x140015208  nop     dword ptr [rax+rax+00h]
0x14001520d  movzx   eax, ax
0x140015210  jmp     short loc_140015215
0x140015212  add     eax, 0FFFFFFE0h
0x140015215  rol     edi, 1
0x140015217  xor     edi, eax
0x140015219  add     rbx, 2
0x14001521d  cmp     rbx, rsi
0x140015220  jb      short loc_1400151F1
0x140015222  mov     ebp, edi
0x140015224  lea     rcx, LuafvDvfcbHashTable
0x14001522b  ror     ebp, 8
0x14001522e  xor     edx, edx
0x140015230  xor     ebp, edi
0x140015232  mov     eax, ebp
0x140015234  mov     [r13+0], ebp
0x140015238  and     eax, 0Fh
0x14001523b  lea     rax, [rax+rax*2]
0x14001523f  lea     rdi, [rcx+rax*8]
0x140015243  lea     r15, [rdi+10h]
0x140015247  mov     rcx, r15
0x14001524a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140015251  nop     dword ptr [rax+rax+00h]
0x140015256  mov     rsi, [rdi]
0x140015259  mov     r12d, 1
0x14001525f  cmp     rsi, rdi
0x140015262  jz      short loc_14001529E
0x140015264  lea     rbx, [rsi-8]
0x140015268  cmp     [rbx+38h], ebp
0x14001526b  jnz     short loc_140015290
0x14001526d  movzx   eax, word ptr [r14]
0x140015271  lea     rcx, [rbx+28h]; String1
0x140015275  cmp     [rcx], ax
0x140015278  jnz     short loc_140015290
0x14001527a  mov     r8b, r12b; CaseInSensitive
0x14001527d  mov     rdx, r14; String2
0x140015280  call    cs:__imp_RtlEqualUnicodeString
0x140015287  nop     dword ptr [rax+rax+00h]
0x14001528c  test    al, al
0x14001528e  jnz     short loc_140015295
0x140015290  mov     rsi, [rsi]
0x140015293  jmp     short loc_14001525F
0x140015295  lock add [rbx], r12d
0x140015299  jmp     loc_140015359
0x14001529e  movzx   esi, word ptr [r14]
0x1400152a2  mov     r8b, 7
0x1400152a5  add     esi, 7Ah ; 'z'
0x1400152a8  mov     ecx, r12d
0x1400152ab  mov     edx, esi
0x1400152ad  call    LuafvAllocatePool
0x1400152b2  mov     rbx, rax
0x1400152b5  test    rax, rax
0x1400152b8  jz      loc_140015359
0x1400152be  lock add cs:LuafvActiveDvfcbCount, r12d
0x1400152c6  mov     r8d, esi; Size
0x1400152c9  xor     edx, edx; Val
0x1400152cb  mov     rcx, rbx; void *
0x1400152ce  call    memset
0x1400152d3  mov     [rbx], r12d
0x1400152d6  lea     rax, [rbx+18h]
0x1400152da  mov     [rax+8], rax
0x1400152de  lea     rcx, [rbx+78h]; void *
0x1400152e2  mov     [rax], rax
0x1400152e5  movzx   eax, word ptr [r14]
0x1400152e9  mov     [rbx+28h], ax
0x1400152ed  movzx   eax, word ptr [r14]
0x1400152f1  mov     [rbx+30h], rcx
0x1400152f5  add     ax, 2
0x1400152f9  mov     [rbx+2Ah], ax
0x1400152fd  movzx   r8d, word ptr [r14]; Size
0x140015301  mov     rdx, [r14+8]; Src
0x140015305  call    memmove
0x14001530a  movzx   r8d, word ptr [r14]
0x14001530e  lea     rcx, [rbx+40h]; PushLock
0x140015312  mov     rdx, [rbx+30h]
0x140015316  xor     eax, eax
0x140015318  shr     r8, 1
0x14001531b  mov     [rdx+r8*2], ax
0x140015320  mov     [rbx+38h], ebp
0x140015323  call    cs:__imp_FltInitializePushLock
0x14001532a  nop     dword ptr [rax+rax+00h]
0x14001532f  mov     qword ptr [rbx+70h], 0
0x140015337  mov     rdx, [rdi]
0x14001533a  cmp     [rdx+8], rdi
0x14001533e  jz      short loc_140015347
0x140015340  mov     ecx, 3
0x140015345  int     29h; Win8: RtlFailFast(ecx)
0x140015347  lea     rax, [rbx+8]
0x14001534b  mov     [rax], rdx
0x14001534e  mov     [rax+8], rdi
0x140015352  mov     [rdx+8], rax
0x140015356  mov     [rdi], rax
0x140015359  xor     edx, edx
0x14001535b  mov     rcx, r15
0x14001535e  call    cs:__imp_FltReleasePushLockEx
0x140015365  nop     dword ptr [rax+rax+00h]
0x14001536a  mov     rax, rbx
0x14001536d  add     rsp, 28h
0x140015371  pop     r15
0x140015373  pop     r14
0x140015375  pop     r13
0x140015377  pop     r12
0x140015379  pop     rdi
0x14001537a  pop     rsi
0x14001537b  pop     rbp
0x14001537c  pop     rbx
0x14001537d  retn
```
