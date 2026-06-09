# ccabFromSession

- ea: `0x140004398`
- end: `0x1400045a3`
- name: `ccabFromSession`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400052b0`
- `0x140005860`

## callees

- `0x140004398`
- `0x1400068d8`
- `0x1400072bc`
- `0x14000c3a8`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atol` at `0x1400044e0`
- `msvcrt!atol` at `0x140004521`
- `msvcrt!atol` at `0x1400044e0`
- `msvcrt!atol` at `0x140004521`
- `msvcrt!atoi` at `0x1400043d5`
- `msvcrt!atoi` at `0x1400044d4`
- `msvcrt!atoi` at `0x140004515`
- `msvcrt!atoi` at `0x1400043d5`
- `msvcrt!atoi` at `0x1400044d4`
- `msvcrt!atoi` at `0x140004515`

## string_xrefs

- `0x140004451`: `CabinetNameTemplate`

## pseudocode

```c
_BOOL8 __fastcall ccabFromSession(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v8; // rax
  BOOL v9; // r9d
  __int64 v10; // r8
  int v11; // r15d
  __int64 v12; // r14
  _BYTE *v13; // r8
  __int64 v14; // rsi
  _BYTE *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  _BYTE *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  _BYTE *v24; // rax
  _BYTE *v25; // rdi
  _BYTE *v26; // rax

  *(_DWORD *)(a2 + 64) = a3;
  v8 = VarFind(*(_QWORD *)(a2 + 16), "LongSourceFileNames", a4);
  v9 = !*(_DWORD *)(a4 + 512) && atoi(*(const char **)(v8 + 8));
  if ( !newDiskIfNecessary(a2, a3, 0, v9, a4) )
    return 0;
  ++*(_DWORD *)(a2 + 40);
  v11 = a1 + 290;
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 36);
  *(_WORD *)(a1 + 32) = *(_WORD *)(a2 + 164);
  *(_DWORD *)(a1 + 28) = 0;
  if ( !(unsigned int)getVarWithOverride(
                        a2,
                        a1 + 290,
                        v10,
                        "CabinetName*",
                        "CabinetNameTemplate",
                        *(_DWORD *)(a2 + 40),
                        "cabinet file name",
                        a4) )
    return 0;
  v12 = 2147483646;
  v13 = (_BYTE *)(a2 + 2868);
  v14 = 256;
  v15 = (_BYTE *)(a1 + 546);
  v16 = 2147483646;
  v17 = 256;
  do
  {
    if ( !v16 )
      break;
    if ( !*v13 )
      break;
    *v15++ = *v13++;
    --v16;
    --v17;
  }
  while ( v17 );
  v18 = v15 - 1;
  if ( v17 )
    v18 = v15;
  *v18 = 0;
  v19 = VarFind(*(_QWORD *)(a2 + 16), "MaxCabinetSize", a4);
  if ( v19 )
    v20 = atol(*(const char **)(v19 + 8));
  else
    v20 = atoi("0");
  *(_DWORD *)a1 = v20;
  if ( !v20 || v20 > *(_DWORD *)(a2 + 48) )
    *(_DWORD *)a1 = *(_DWORD *)(a2 + 48);
  v21 = VarFind(*(_QWORD *)(a2 + 16), "FolderSizeThreshold", a4);
  if ( v21 )
    v22 = atol(*(const char **)(v21 + 8));
  else
    v22 = atoi("0");
  *(_DWORD *)(a1 + 4) = v22;
  if ( !v22 )
  {
    v23 = *(_DWORD *)a1;
    if ( !*(_DWORD *)a1 )
      v23 = 0x7FFFFFFF;
    *(_DWORD *)(a1 + 4) = v23;
  }
  v24 = (_BYTE *)(a2 + 2612);
  v25 = (_BYTE *)(a1 + 34);
  do
  {
    if ( !v12 )
      break;
    if ( !*v24 )
      break;
    *v25++ = *v24++;
    --v12;
    --v14;
  }
  while ( v14 );
  v26 = v25 - 1;
  if ( v14 )
    v26 = v25;
  *v26 = 0;
  return (unsigned int)infAddCabinet(a2, *(_DWORD *)(a2 + 40), *(_DWORD *)(a2 + 36), v11, a4) != 0;
}

```

## disassembly

```asm
0x140004398  push    rbx
0x14000439a  push    rbp
0x14000439b  push    rsi
0x14000439c  push    rdi
0x14000439d  push    r14
0x14000439f  push    r15
0x1400043a1  sub     rsp, 48h
0x1400043a5  mov     rbx, rdx
0x1400043a8  mov     [rdx+40h], r8d
0x1400043ac  mov     esi, r8d
0x1400043af  lea     rdx, aLongsourcefile_0; "LongSourceFileNames"
0x1400043b6  mov     rdi, rcx
0x1400043b9  mov     r8, r9
0x1400043bc  mov     rbp, r9
0x1400043bf  mov     rcx, [rbx+10h]
0x1400043c3  call    VarFind
0x1400043c8  cmp     dword ptr [rbp+200h], 0
0x1400043cf  jnz     short loc_1400043E7
0x1400043d1  mov     rcx, [rax+8]; String
0x1400043d5  call    cs:__imp_atoi
0x1400043db  test    eax, eax
0x1400043dd  jz      short loc_1400043E7
0x1400043df  mov     r9d, 1
0x1400043e5  jmp     short loc_1400043EA
0x1400043e7  xor     r9d, r9d
0x1400043ea  xor     r8d, r8d
0x1400043ed  mov     [rsp+78h+var_58], rbp
0x1400043f2  mov     edx, esi
0x1400043f4  mov     rcx, rbx
0x1400043f7  call    newDiskIfNecessary
0x1400043fc  test    eax, eax
0x1400043fe  jz      loc_140004594
0x140004404  inc     dword ptr [rbx+28h]
0x140004407  lea     r15, [rdi+122h]
0x14000440e  mov     eax, [rbx+28h]
0x140004411  lea     r9, aCabinetname; "CabinetName*"
0x140004418  mov     [rdi+14h], eax
0x14000441b  mov     rdx, r15
0x14000441e  mov     eax, [rbx+24h]
0x140004421  mov     rcx, rbx
0x140004424  mov     [rdi+18h], eax
0x140004427  movzx   eax, word ptr [rbx+0A4h]
0x14000442e  mov     [rdi+20h], ax
0x140004432  lea     rax, aCabinetFileNam; "cabinet file name"
0x140004439  mov     [rsp+78h+var_40], rbp
0x14000443e  mov     [rsp+78h+var_48], rax
0x140004443  mov     dword ptr [rdi+1Ch], 0
0x14000444a  mov     eax, [rbx+28h]
0x14000444d  mov     [rsp+78h+var_50], eax
0x140004451  lea     rax, aCabinetnametem; "CabinetNameTemplate"
0x140004458  mov     [rsp+78h+var_58], rax
0x14000445d  call    getVarWithOverride
0x140004462  test    eax, eax
0x140004464  jz      loc_140004594
0x14000446a  mov     r14d, 7FFFFFFEh
0x140004470  lea     r8, [rbx+0B34h]
0x140004477  mov     esi, 100h
0x14000447c  lea     rcx, [rdi+222h]
0x140004483  mov     eax, r14d
0x140004486  mov     edx, esi
0x140004488  test    rax, rax
0x14000448b  jz      short loc_1400044A7
0x14000448d  mov     r9b, [r8]
0x140004490  test    r9b, r9b
0x140004493  jz      short loc_1400044A7
0x140004495  mov     [rcx], r9b
0x140004498  inc     r8
0x14000449b  inc     rcx
0x14000449e  dec     rax
0x1400044a1  sub     rdx, 1
0x1400044a5  jnz     short loc_140004488
0x1400044a7  test    rdx, rdx
0x1400044aa  lea     rax, [rcx-1]
0x1400044ae  mov     r8, rbp
0x1400044b1  lea     rdx, aMaxcabinetsize; "MaxCabinetSize"
0x1400044b8  cmovnz  rax, rcx
0x1400044bc  mov     byte ptr [rax], 0
0x1400044bf  mov     rcx, [rbx+10h]
0x1400044c3  call    VarFind
0x1400044c8  test    rax, rax
0x1400044cb  jnz     short loc_1400044DC
0x1400044cd  lea     rcx, a0; "0"
0x1400044d4  call    cs:__imp_atoi
0x1400044da  jmp     short loc_1400044E6
0x1400044dc  mov     rcx, [rax+8]; String
0x1400044e0  call    cs:__imp_atol
0x1400044e6  mov     [rdi], eax
0x1400044e8  test    eax, eax
0x1400044ea  jz      short loc_1400044F1
0x1400044ec  cmp     eax, [rbx+30h]
0x1400044ef  jbe     short loc_1400044F6
0x1400044f1  mov     eax, [rbx+30h]
0x1400044f4  mov     [rdi], eax
0x1400044f6  mov     rcx, [rbx+10h]
0x1400044fa  lea     rdx, aFoldersizethre; "FolderSizeThreshold"
0x140004501  mov     r8, rbp
0x140004504  call    VarFind
0x140004509  test    rax, rax
0x14000450c  jnz     short loc_14000451D
0x14000450e  lea     rcx, a0; "0"
0x140004515  call    cs:__imp_atoi
0x14000451b  jmp     short loc_140004527
0x14000451d  mov     rcx, [rax+8]; String
0x140004521  call    cs:__imp_atol
0x140004527  mov     [rdi+4], eax
0x14000452a  test    eax, eax
0x14000452c  jnz     short loc_14000453D
0x14000452e  mov     eax, [rdi]
0x140004530  mov     ecx, 7FFFFFFFh
0x140004535  test    eax, eax
0x140004537  cmovz   eax, ecx
0x14000453a  mov     [rdi+4], eax
0x14000453d  lea     rax, [rbx+0A34h]
0x140004544  add     rdi, 22h ; '"'
0x140004548  test    r14, r14
0x14000454b  jz      short loc_140004564
0x14000454d  mov     cl, [rax]
0x14000454f  test    cl, cl
0x140004551  jz      short loc_140004564
0x140004553  mov     [rdi], cl
0x140004555  inc     rax
0x140004558  inc     rdi
0x14000455b  dec     r14
0x14000455e  sub     rsi, 1
0x140004562  jnz     short loc_140004548
0x140004564  test    rsi, rsi
0x140004567  mov     [rsp+78h+var_58], rbp
0x14000456c  lea     rax, [rdi-1]
0x140004570  mov     r9, r15
0x140004573  cmovnz  rax, rdi
0x140004577  mov     rcx, rbx
0x14000457a  mov     byte ptr [rax], 0
0x14000457d  mov     r8d, [rbx+24h]
0x140004581  mov     edx, [rbx+28h]
0x140004584  call    infAddCabinet
0x140004589  xor     ecx, ecx
0x14000458b  test    eax, eax
0x14000458d  setnz   cl
0x140004590  mov     eax, ecx
0x140004592  jmp     short loc_140004596
0x140004594  xor     eax, eax
0x140004596  add     rsp, 48h
0x14000459a  pop     r15
0x14000459c  pop     r14
0x14000459e  pop     rdi
0x14000459f  pop     rsi
0x1400045a0  pop     rbp
0x1400045a1  pop     rbx
0x1400045a2  retn
```
