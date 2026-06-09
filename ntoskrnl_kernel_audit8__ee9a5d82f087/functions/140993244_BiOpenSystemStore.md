# BiOpenSystemStore

- ea: `0x140993244`
- end: `0x1409934e7`
- name: `BiOpenSystemStore`
- size: `675`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14072fda8`
- `0x140737268`

## callees

- `0x140544740`
- `0x1405469e0`
- `0x1406dd5c0`
- `0x14098eb74`
- `0x14098eeb8`
- `0x14098efbc`
- `0x140991464`
- `0x14099265c`
- `0x140992794`
- `0x140992aa8`
- `0x140993244`
- `0x1409935a8`
- `0x140993780`
- `0x140993794`
- `0x140994f7c`
- `0x140995510`
- `0x140aea6a4`
- `0x140bb19f0`

## string_xrefs

- `0x1409932a7`: `\Registry\Machine`
- `0x14099349e`: `Specified flags prevent opening unloaded system store`
- `0x1409933ea`: `The system store is not already loaded`
- `0x140993278`: `Opening system store. Flags: 0x%x`

## pseudocode

```c
__int64 __fastcall BiOpenSystemStore(unsigned __int64 *a1, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  char v4; // r8
  int v5; // ebx
  int v7; // eax
  _QWORD *v8; // r14
  __int64 i; // rsi
  bool v10; // zf
  int v11; // r15d
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HANDLE Handle[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+48h] BYREF
  PVOID P; // [rsp+80h] [rbp+50h] BYREF
  HANDLE v23; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  *a1 = 0;
  v21 = 0;
  Handle[0] = 0;
  v23 = 0;
  P = 0;
  BiLogMessage(2, L"Opening system store. Flags: 0x%x", a2);
  BiCleanupLoadedStores(16 * (v4 & 1u));
  v5 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, Handle);
  if ( v5 < 0 )
    goto LABEL_2;
  v7 = BiEnumerateSubKeys(Handle[0], &P, &v21);
  v8 = P;
  v5 = v7;
  if ( v7 >= 0 )
  {
    LODWORD(P) = 0;
    v5 = -1073741275;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v10 = (_DWORD)i == v21;
      if ( (unsigned int)i >= v21 )
        break;
      if ( !wcsnicmp((const wchar_t *)v8[i], L"BCD", 3u) && wcstoul((const wchar_t *)(v8[i] + 6LL), 0, 10) != -1 )
      {
        BiLogMessage(2, L"Found loaded store at key %s", v8[i]);
        v18 = BiOpenKey(Handle[0], v8[i], 131097, &v23);
        v2 = (unsigned __int64)v23;
        v5 = v18;
        if ( v18 >= 0 )
        {
          if ( (unsigned __int8)BiIsSystemStore(v23) )
          {
            BiLogMessage(2, L"Store %s is the system store", v8[i]);
            v5 = 0;
            v10 = (_DWORD)i == v21;
            break;
          }
          BiCloseKey((HANDLE)v2);
        }
      }
    }
    if ( v10 )
    {
      BiLogMessage(2, L"The system store is not already loaded");
      v23 = 0;
      if ( (a2 & 4) != 0 )
      {
        BiLogMessage(4, L"Specified flags prevent opening unloaded system store");
        v5 = -1073741275;
        goto LABEL_20;
      }
      v17 = BiLoadSystemStore(&v23);
      v2 = (unsigned __int64)v23;
      v5 = v17;
      if ( v17 < 0 )
      {
        v11 = (int)P;
        goto LABEL_18;
      }
      v11 = 1;
    }
    else
    {
      v11 = (int)P;
    }
    if ( (a2 & 2) != 0 )
    {
      v2 |= 2u;
      goto LABEL_29;
    }
    v12 = (unsigned __int8)BiWasFirmwareModified(v2);
    BiLogMessage(2, L"Synchronizing store with firmware. FirmwareModified: %d", v12);
    v13 = BiGetFirmwareType(0) - 1;
    if ( v13 )
    {
      v16 = v13 - 1;
      if ( !v16 )
      {
        v5 = BiBindEfiNamespaceObjects(v2);
        v15 = (unsigned int)v5;
        if ( v5 < 0 )
        {
LABEL_17:
          BiLogMessage(4, L"Failed to bind with firmware. Flags: 0x%x Status: %x", a2, v15);
          goto LABEL_18;
        }
        goto LABEL_36;
      }
      if ( v16 != 1 )
      {
        v5 = -1073741637;
        v15 = 3221225659LL;
        goto LABEL_17;
      }
    }
    v5 = 0;
LABEL_36:
    if ( !(_BYTE)v12 )
      BiSetFirmwareModified(v2, 0, v14, v15);
LABEL_29:
    *a1 = v2;
    if ( v5 >= 0 )
      goto LABEL_20;
LABEL_18:
    if ( v2 )
      BiCloseStore(v2, v11 != 0 ? 2 : 0);
  }
LABEL_20:
  if ( v8 )
    ExFreePoolWithTag(v8, 0x4B444342u);
LABEL_2:
  if ( Handle[0] )
    ZwClose(Handle[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140993244  mov     [rsp-38h+arg_0], rcx
0x140993249  push    rbp
0x14099324a  push    rbx
0x14099324b  push    rsi
0x14099324c  push    rdi
0x14099324d  push    r13
0x14099324f  push    r14
0x140993251  push    r15
0x140993253  mov     rbp, rsp
0x140993256  sub     rsp, 30h
0x14099325a  xor     edi, edi
0x14099325c  mov     qword ptr [rcx], 0
0x140993263  mov     r8d, edx
0x140993266  mov     [rbp+arg_8], 0
0x14099326d  mov     r13d, edx
0x140993270  mov     [rbp+Handle], 0
0x140993278  lea     rdx, aOpeningSystemS; "Opening system store. Flags: 0x%x"
0x14099327f  mov     [rbp+arg_18], rdi
0x140993283  lea     ecx, [rdi+2]
0x140993286  mov     [rbp+P], rdi
0x14099328a  call    BiLogMessage
0x14099328f  mov     ecx, r8d
0x140993292  and     ecx, 1
0x140993295  shl     ecx, 4
0x140993298  call    BiCleanupLoadedStores
0x14099329d  lea     r9, [rbp+Handle]
0x1409932a1  mov     r8d, 0F003Fh
0x1409932a7  lea     rdx, aRegistryMachin_230; "\\Registry\\Machine"
0x1409932ae  xor     ecx, ecx
0x1409932b0  call    BiOpenKeyNonBcd
0x1409932b5  mov     ebx, eax
0x1409932b7  test    eax, eax
0x1409932b9  jns     short loc_1409932DD
0x1409932bb  cmp     [rbp+Handle], 0
0x1409932c0  jz      short loc_1409932CB
0x1409932c2  mov     rcx, [rbp+Handle]; Handle
0x1409932c6  call    ZwClose
0x1409932cb  mov     eax, ebx
0x1409932cd  add     rsp, 30h
0x1409932d1  pop     r15
0x1409932d3  pop     r14
0x1409932d5  pop     r13
0x1409932d7  pop     rdi
0x1409932d8  pop     rsi
0x1409932d9  pop     rbx
0x1409932da  pop     rbp
0x1409932db  retn
0x1409932dd  mov     rcx, [rbp+Handle]
0x1409932e1  lea     r8, [rbp+arg_8]
0x1409932e5  lea     rdx, [rbp+P]
0x1409932e9  call    BiEnumerateSubKeys
0x1409932ee  mov     r14, [rbp+P]
0x1409932f2  mov     ebx, eax
0x1409932f4  test    eax, eax
0x1409932f6  js      loc_1409933CF
0x1409932fc  mov     dword ptr [rbp+P], edi
0x1409932ff  mov     ebx, 0C0000225h
0x140993304  xor     esi, esi
0x140993306  cmp     esi, [rbp+arg_8]
0x140993309  jnb     short loc_140993345
0x14099330b  mov     rcx, [r14+rsi*8]; Str1
0x14099330f  lea     rdx, aBcd; "BCD"
0x140993316  mov     r8d, 3; MaxCount
0x14099331c  call    _wcsnicmp
0x140993321  test    eax, eax
0x140993323  jnz     short loc_140993341
0x140993325  mov     rcx, [r14+rsi*8]
0x140993329  lea     r8d, [rax+0Ah]; Radix
0x14099332d  add     rcx, 6; Str
0x140993331  xor     edx, edx; EndPtr
0x140993333  call    wcstoul
0x140993338  cmp     eax, 0FFFFFFFFh
0x14099333b  jnz     loc_14099342F
0x140993341  inc     esi
0x140993343  jmp     short loc_140993306
0x140993345  jz      loc_1409933EA
0x14099334b  mov     r15d, dword ptr [rbp+P]
0x14099334f  test    r13b, 2
0x140993353  jnz     loc_140993486
0x140993359  mov     rcx, rdi
0x14099335c  call    BiWasFirmwareModified
0x140993361  movzx   esi, al
0x140993364  lea     rdx, aSynchronizingS; "Synchronizing store with firmware. Firm"...
0x14099336b  mov     r8d, esi
0x14099336e  mov     ecx, 2
0x140993373  call    BiLogMessage
0x140993378  xor     ecx, ecx
0x14099337a  call    BiGetFirmwareType
0x14099337f  sub     eax, 1
0x140993382  jz      loc_1409934D4
0x140993388  sub     eax, 1
0x14099338b  jnz     loc_1409934C2
0x140993391  mov     rcx, rdi
0x140993394  call    BiBindEfiNamespaceObjects
0x140993399  mov     ebx, eax
0x14099339b  mov     r9d, eax
0x14099339e  test    eax, eax
0x1409933a0  jns     loc_1409934D6
0x1409933a6  mov     r8d, r13d
0x1409933a9  lea     rdx, aFailedToBindWi; "Failed to bind with firmware. Flags: 0x"...
0x1409933b0  mov     ecx, 4
0x1409933b5  call    BiLogMessage
0x1409933ba  test    rdi, rdi
0x1409933bd  jz      short loc_1409933CF
0x1409933bf  neg     r15d
0x1409933c2  mov     rcx, rdi
0x1409933c5  sbb     edx, edx
0x1409933c7  and     edx, 2
0x1409933ca  call    BiCloseStore
0x1409933cf  test    r14, r14
0x1409933d2  jz      loc_1409932BB
0x1409933d8  mov     edx, 4B444342h; Tag
0x1409933dd  mov     rcx, r14; P
0x1409933e0  call    ExFreePoolWithTag
0x1409933e5  jmp     loc_1409932BB
0x1409933ea  lea     rdx, aTheSystemStore; "The system store is not already loaded"
0x1409933f1  mov     ecx, 2
0x1409933f6  call    BiLogMessage
0x1409933fb  mov     [rbp+arg_18], 0
0x140993403  test    r13b, 4
0x140993407  jnz     loc_14099349E
0x14099340d  lea     rcx, [rbp+arg_18]
0x140993411  call    BiLoadSystemStore
0x140993416  mov     rdi, [rbp+arg_18]
0x14099341a  mov     ebx, eax
0x14099341c  test    eax, eax
0x14099341e  js      loc_1409934B9
0x140993424  mov     r15d, 1
0x14099342a  jmp     loc_14099334F
0x14099342f  mov     r8, [r14+rsi*8]
0x140993433  lea     rdx, aFoundLoadedSto; "Found loaded store at key %s"
0x14099343a  mov     ecx, 2
0x14099343f  call    BiLogMessage
0x140993444  mov     rdx, [r14+rsi*8]
0x140993448  lea     r9, [rbp+arg_18]
0x14099344c  mov     rcx, [rbp+Handle]
0x140993450  mov     r8d, 20019h
0x140993456  call    BiOpenKey
0x14099345b  mov     rdi, [rbp+arg_18]
0x14099345f  mov     ebx, eax
0x140993461  test    eax, eax
0x140993463  js      loc_140993341
0x140993469  mov     rcx, rdi
0x14099346c  call    BiIsSystemStore
0x140993471  test    al, al
0x140993473  jnz     loc_140B6354A
0x140993479  mov     rcx, rdi; Handle
0x14099347c  call    BiCloseKey
0x140993481  jmp     loc_140993341
0x140993486  or      rdi, 2
0x14099348a  mov     rax, [rbp+arg_0]
0x14099348e  mov     [rax], rdi
0x140993491  test    ebx, ebx
0x140993493  js      loc_1409933BA
0x140993499  jmp     loc_1409933CF
0x14099349e  lea     rdx, aSpecifiedFlags; "Specified flags prevent opening unloade"...
0x1409934a5  mov     ecx, 4
0x1409934aa  call    BiLogMessage
0x1409934af  mov     ebx, 0C0000225h
0x1409934b4  jmp     loc_1409933CF
0x1409934b9  mov     r15d, dword ptr [rbp+P]
0x1409934bd  jmp     loc_1409933BA
0x1409934c2  cmp     eax, 1
0x1409934c5  jz      short loc_1409934D4
0x1409934c7  mov     ebx, 0C00000BBh
0x1409934cc  mov     r9d, ebx
0x1409934cf  jmp     loc_1409933A6
0x1409934d4  xor     ebx, ebx
0x1409934d6  test    sil, sil
0x1409934d9  jnz     short loc_14099348A
0x1409934db  xor     edx, edx
0x1409934dd  mov     rcx, rdi
0x1409934e0  call    BiSetFirmwareModified
0x1409934e5  jmp     short loc_14099348A
0x140b6354a  mov     r8, [r14+rsi*8]
0x140b6354e  lea     rdx, aStoreSIsTheSys; "Store %s is the system store"
0x140b63555  mov     ecx, 2
0x140b6355a  call    BiLogMessage
0x140b6355f  xor     ebx, ebx
0x140b63561  cmp     esi, [rbp+arg_8]
0x140b63564  jmp     loc_140993345
```
