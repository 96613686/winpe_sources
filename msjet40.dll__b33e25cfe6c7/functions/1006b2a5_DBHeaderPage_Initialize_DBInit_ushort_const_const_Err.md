# DBHeaderPage::Initialize(DBInit &,ushort const * const,Err &)

- ea: `0x1006b2a5`
- end: `0x1006b431`
- name: `?Initialize@DBHeaderPage@@QAEKAAUDBInit@@QBGAAVErr@@@Z`
- size: `396`
- prototype: `unsigned int __thiscall(DBHeaderPage *__hidden this, struct DBInit *, const unsigned __int16 *const, struct Err *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100546f8`

## callees

- `0x100269c0`
- `0x100462a4`
- `0x1006b2a5`
- `0x1007a4e0`
- `0x1007a560`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1006b346`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1006b346`

## string_xrefs

- `0x1006b30a`: `Temp Jet DB    `

## pseudocode

```c
unsigned int __thiscall DBHeaderPage::Initialize(
        DBHeaderPage *this,
        struct DBInit *a2,
        const unsigned __int16 *a3,
        struct Err *a4)
{
  int v4; // ebx
  unsigned int i; // eax
  struct DBInit *v6; // edx
  const char *v7; // esi
  _DWORD *v8; // esi
  unsigned int v9; // edi
  DWORD TickCount; // eax
  double v11; // xmm0_8
  unsigned int j; // edi
  int v13; // eax
  unsigned int v14; // edi
  int v15; // edx
  size_t v17; // [esp+0h] [ebp-134h]
  const char *v18; // [esp+4h] [ebp-130h]
  double v19; // [esp+10h] [ebp-124h] BYREF
  unsigned __int8 *v20; // [esp+18h] [ebp-11Ch]
  unsigned int v21; // [esp+1Ch] [ebp-118h]
  _BYTE v22[268]; // [esp+20h] [ebp-114h] BYREF

  v4 = *((_DWORD *)this + 1);
  Encryption::Encryption((Encryption *)v22, 0x6B39DAC7u);
  memset((void *)(v4 + 4), 0, 0xFFCu);
  for ( i = 0; i < 0x100; ++i )
    *(_WORD *)(v4 + 2 * i + 3584) = 256;
  v6 = a2;
  *(_DWORD *)v4 = 256;
  *(_DWORD *)(v4 + 20) = *((_DWORD *)a2 + 1);
  if ( *(_DWORD *)a2 == 1 )
  {
    v7 = "Temp Jet DB    ";
  }
  else
  {
    v7 = "Jet System DB  ";
    if ( *(_DWORD *)a2 != 4 )
      v7 = "Standard Jet DB";
  }
  *(_DWORD *)(v4 + 4) = *(_DWORD *)v7;
  v8 = v7 + 4;
  v20 = (unsigned __int8 *)(v4 + 24);
  *(_DWORD *)(v4 + 8) = *v8++;
  *(_DWORD *)(v4 + 12) = *v8;
  *(_DWORD *)(v4 + 16) = v8[1];
  *(_DWORD *)(v4 + 24) = *((_DWORD *)a2 + 2);
  *(_DWORD *)(v4 + 28) = *((_DWORD *)a2 + 3);
  if ( *(_DWORD *)a2 == 3 || *(_DWORD *)a2 == 4 )
  {
    TickCount = GetTickCount();
    v6 = a2;
    v9 = TickCount | 0xA0A00000;
  }
  else
  {
    v9 = 0;
  }
  v21 = v9;
  *(_DWORD *)(v4 + 62) = v9;
  if ( a3 )
    qmemcpy((void *)(v4 + 66), a3, 0x28u);
  *(_DWORD *)(v4 + 106) = 9801;
  *(_DWORD *)(v4 + 110) = *((_DWORD *)v6 + 4);
  *(_WORD *)(v4 + 60) = *((_WORD *)v6 + 10);
  UtilGetDateTime(&v19);
  v11 = v19;
  if ( v19 == 0.0 )
    v11 = DOUBLE_1_0;
  *(double *)(v4 + 114) = v11;
  for ( j = 0; j < 0x20; ++j )
  {
    *(_DWORD *)(v4 + 16 * j + 152) = dword_1000B508[4 * j];
    StringCchCopyA((STRSAFE_LPSTR)&dword_1000B50C[4 * j], v17, v18);
    if ( !dword_1000B508[4 * j] )
      break;
  }
  v13 = (int)*(double *)(v4 + 114);
  v14 = v21;
  v15 = 0;
  do
  {
    *(_DWORD *)(v4 + v15 + 66) ^= v13;
    v15 += 4;
  }
  while ( v15 + 4 <= 40 );
  Encryption::Encrypt((Encryption *)v22, v20, 0x80u);
  return v14;
}

```

## disassembly

```asm
0x1006b2a5  mov     edi, edi
0x1006b2a7  push    ebp
0x1006b2a8  mov     ebp, esp
0x1006b2aa  sub     esp, 128h
0x1006b2b0  mov     eax, ___security_cookie
0x1006b2b5  xor     eax, ebp
0x1006b2b7  mov     [ebp+var_8], eax
0x1006b2ba  push    ebx
0x1006b2bb  mov     ebx, [ecx+4]
0x1006b2be  lea     ecx, [ebp+var_114]; this
0x1006b2c4  push    esi; pszSrc
0x1006b2c5  push    edi; cchDest
0x1006b2c6  push    6B39DAC7h; unsigned int
0x1006b2cb  call    ??0Encryption@@QAE@K@Z; Encryption::Encryption(ulong)
0x1006b2d0  push    0FFCh; Size
0x1006b2d5  lea     eax, [ebx+4]
0x1006b2d8  push    0; Val
0x1006b2da  push    eax; void *
0x1006b2db  call    _memset
0x1006b2e0  add     esp, 0Ch
0x1006b2e3  mov     ecx, 100h
0x1006b2e8  xor     eax, eax
0x1006b2ea  mov     [ebx+eax*2+0E00h], cx
0x1006b2f2  inc     eax
0x1006b2f3  cmp     eax, ecx
0x1006b2f5  jb      short loc_1006B2EA
0x1006b2f7  mov     edx, [ebp+arg_0]
0x1006b2fa  lea     edi, [ebx+4]
0x1006b2fd  mov     [ebx], ecx
0x1006b2ff  mov     eax, [edx+4]
0x1006b302  mov     [ebx+14h], eax
0x1006b305  cmp     dword ptr [edx], 1
0x1006b308  jnz     short loc_1006B311
0x1006b30a  mov     esi, offset aTempJetDb; "Temp Jet DB    "
0x1006b30f  jmp     short loc_1006B320
0x1006b311  cmp     dword ptr [edx], 4
0x1006b314  mov     esi, offset aJetSystemDb; "Jet System DB  "
0x1006b319  jz      short loc_1006B320
0x1006b31b  mov     esi, offset aStandardJetDb; "Standard Jet DB"
0x1006b320  movsd
0x1006b321  lea     ecx, [ebx+18h]
0x1006b324  mov     [ebp+var_11C], ecx
0x1006b32a  movsd
0x1006b32b  movsd
0x1006b32c  movsd
0x1006b32d  mov     eax, [edx+8]
0x1006b330  mov     [ecx], eax
0x1006b332  mov     eax, [edx+0Ch]
0x1006b335  mov     [ebx+1Ch], eax
0x1006b338  cmp     dword ptr [edx], 3
0x1006b33b  jz      short loc_1006B346
0x1006b33d  cmp     dword ptr [edx], 4
0x1006b340  jz      short loc_1006B346
0x1006b342  xor     edi, edi
0x1006b344  jmp     short loc_1006B357
0x1006b346  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1006b34c  mov     edx, [ebp+arg_0]
0x1006b34f  mov     edi, eax
0x1006b351  or      edi, 0A0A00000h
0x1006b357  mov     esi, [ebp+arg_4]
0x1006b35a  mov     [ebp+var_118], edi
0x1006b360  mov     [ebx+3Eh], edi
0x1006b363  test    esi, esi
0x1006b365  jz      short loc_1006B36F
0x1006b367  push    0Ah
0x1006b369  lea     edi, [ebx+42h]
0x1006b36c  pop     ecx
0x1006b36d  rep movsd
0x1006b36f  mov     dword ptr [ebx+6Ah], 2649h
0x1006b376  lea     ecx, [ebp+var_124]
0x1006b37c  mov     eax, [edx+10h]
0x1006b37f  mov     [ebx+6Eh], eax
0x1006b382  mov     ax, [edx+14h]
0x1006b386  mov     [ebx+3Ch], ax
0x1006b38a  call    _UtilGetDateTime@4; UtilGetDateTime(x)
0x1006b38f  movsd   xmm0, [ebp+var_124]
0x1006b397  ucomisd xmm0, ds:__real@0000000000000000
0x1006b39f  lahf
0x1006b3a0  test    ah, 44h
0x1006b3a3  jp      short loc_1006B3AD
0x1006b3a5  movsd   xmm0, ds:__real@3ff0000000000000
0x1006b3ad  movsd   qword ptr [ebx+72h], xmm0
0x1006b3b2  xor     edi, edi
0x1006b3b4  mov     esi, edi
0x1006b3b6  lea     ecx, [ebx+9Ch]
0x1006b3bc  shl     esi, 4
0x1006b3bf  add     ecx, esi
0x1006b3c1  mov     eax, ds:dword_1000B508[esi]
0x1006b3c7  mov     [ebx+esi+98h], eax
0x1006b3ce  lea     eax, dword_1000B50C[esi]
0x1006b3d4  push    eax; pszDest
0x1006b3d5  push    0Ch
0x1006b3d7  pop     edx
0x1006b3d8  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x1006b3dd  cmp     ds:dword_1000B508[esi], 0
0x1006b3e4  jz      short loc_1006B3EC
0x1006b3e6  inc     edi
0x1006b3e7  cmp     edi, 20h ; ' '
0x1006b3ea  jb      short loc_1006B3B4
0x1006b3ec  cvttsd2si eax, qword ptr [ebx+72h]
0x1006b3f1  mov     edi, [ebp+var_118]
0x1006b3f7  xor     edx, edx
0x1006b3f9  xor     [ebx+edx+42h], eax
0x1006b3fd  lea     edx, [edx+4]
0x1006b400  lea     ecx, [edx+4]
0x1006b403  cmp     ecx, 28h ; '('
0x1006b406  jle     short loc_1006B3F9
0x1006b408  push    80h; unsigned int
0x1006b40d  push    [ebp+var_11C]; unsigned __int8 *
0x1006b413  lea     ecx, [ebp+var_114]; this
0x1006b419  call    ?Encrypt@Encryption@@QAEXPAEI@Z; Encryption::Encrypt(uchar *,uint)
0x1006b41e  mov     ecx, [ebp+var_8]
0x1006b421  mov     eax, edi
0x1006b423  pop     edi
0x1006b424  pop     esi
0x1006b425  xor     ecx, ebp; StackCookie
0x1006b427  pop     ebx
0x1006b428  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006b42d  leave
0x1006b42e  retn    0Ch
```
