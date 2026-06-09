# DBHeaderPage::Initialize(DBInit &,ushort const * const,Err &)

- ea: `0x1006b435`
- end: `0x1006b5c1`
- name: `?Initialize@DBHeaderPage@@QAEKAAUDBInit@@QBGAAVErr@@@Z`
- size: `396`
- prototype: `unsigned int __thiscall(DBHeaderPage *__hidden this, struct DBInit *, const unsigned __int16 *const, struct Err *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10054888`

## callees

- `0x10026b20`
- `0x10046424`
- `0x1006b435`
- `0x1007a670`
- `0x1007a6f0`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1006b4d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1006b4d6`

## string_xrefs

- `0x1006b49a`: `Temp Jet DB    `

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
    *(_DWORD *)(v4 + 16 * j + 152) = dword_1000B5B0[4 * j];
    StringCchCopyA((STRSAFE_LPSTR)&dword_1000B5B4[4 * j], v17, v18);
    if ( !dword_1000B5B0[4 * j] )
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
0x1006b435  mov     edi, edi
0x1006b437  push    ebp
0x1006b438  mov     ebp, esp
0x1006b43a  sub     esp, 128h
0x1006b440  mov     eax, ___security_cookie
0x1006b445  xor     eax, ebp
0x1006b447  mov     [ebp+var_8], eax
0x1006b44a  push    ebx
0x1006b44b  mov     ebx, [ecx+4]
0x1006b44e  lea     ecx, [ebp+var_114]; this
0x1006b454  push    esi; pszSrc
0x1006b455  push    edi; cchDest
0x1006b456  push    6B39DAC7h; unsigned int
0x1006b45b  call    ??0Encryption@@QAE@K@Z; Encryption::Encryption(ulong)
0x1006b460  push    0FFCh; Size
0x1006b465  lea     eax, [ebx+4]
0x1006b468  push    0; Val
0x1006b46a  push    eax; void *
0x1006b46b  call    _memset
0x1006b470  add     esp, 0Ch
0x1006b473  mov     ecx, 100h
0x1006b478  xor     eax, eax
0x1006b47a  mov     [ebx+eax*2+0E00h], cx
0x1006b482  inc     eax
0x1006b483  cmp     eax, ecx
0x1006b485  jb      short loc_1006B47A
0x1006b487  mov     edx, [ebp+arg_0]
0x1006b48a  lea     edi, [ebx+4]
0x1006b48d  mov     [ebx], ecx
0x1006b48f  mov     eax, [edx+4]
0x1006b492  mov     [ebx+14h], eax
0x1006b495  cmp     dword ptr [edx], 1
0x1006b498  jnz     short loc_1006B4A1
0x1006b49a  mov     esi, offset aTempJetDb; "Temp Jet DB    "
0x1006b49f  jmp     short loc_1006B4B0
0x1006b4a1  cmp     dword ptr [edx], 4
0x1006b4a4  mov     esi, offset aJetSystemDb; "Jet System DB  "
0x1006b4a9  jz      short loc_1006B4B0
0x1006b4ab  mov     esi, offset aStandardJetDb; "Standard Jet DB"
0x1006b4b0  movsd
0x1006b4b1  lea     ecx, [ebx+18h]
0x1006b4b4  mov     [ebp+var_11C], ecx
0x1006b4ba  movsd
0x1006b4bb  movsd
0x1006b4bc  movsd
0x1006b4bd  mov     eax, [edx+8]
0x1006b4c0  mov     [ecx], eax
0x1006b4c2  mov     eax, [edx+0Ch]
0x1006b4c5  mov     [ebx+1Ch], eax
0x1006b4c8  cmp     dword ptr [edx], 3
0x1006b4cb  jz      short loc_1006B4D6
0x1006b4cd  cmp     dword ptr [edx], 4
0x1006b4d0  jz      short loc_1006B4D6
0x1006b4d2  xor     edi, edi
0x1006b4d4  jmp     short loc_1006B4E7
0x1006b4d6  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1006b4dc  mov     edx, [ebp+arg_0]
0x1006b4df  mov     edi, eax
0x1006b4e1  or      edi, 0A0A00000h
0x1006b4e7  mov     esi, [ebp+arg_4]
0x1006b4ea  mov     [ebp+var_118], edi
0x1006b4f0  mov     [ebx+3Eh], edi
0x1006b4f3  test    esi, esi
0x1006b4f5  jz      short loc_1006B4FF
0x1006b4f7  push    0Ah
0x1006b4f9  lea     edi, [ebx+42h]
0x1006b4fc  pop     ecx
0x1006b4fd  rep movsd
0x1006b4ff  mov     dword ptr [ebx+6Ah], 2649h
0x1006b506  lea     ecx, [ebp+var_124]
0x1006b50c  mov     eax, [edx+10h]
0x1006b50f  mov     [ebx+6Eh], eax
0x1006b512  mov     ax, [edx+14h]
0x1006b516  mov     [ebx+3Ch], ax
0x1006b51a  call    _UtilGetDateTime@4; UtilGetDateTime(x)
0x1006b51f  movsd   xmm0, [ebp+var_124]
0x1006b527  ucomisd xmm0, ds:__real@0000000000000000
0x1006b52f  lahf
0x1006b530  test    ah, 44h
0x1006b533  jp      short loc_1006B53D
0x1006b535  movsd   xmm0, ds:__real@3ff0000000000000
0x1006b53d  movsd   qword ptr [ebx+72h], xmm0
0x1006b542  xor     edi, edi
0x1006b544  mov     esi, edi
0x1006b546  lea     ecx, [ebx+9Ch]
0x1006b54c  shl     esi, 4
0x1006b54f  add     ecx, esi
0x1006b551  mov     eax, ds:dword_1000B5B0[esi]
0x1006b557  mov     [ebx+esi+98h], eax
0x1006b55e  lea     eax, dword_1000B5B4[esi]
0x1006b564  push    eax; pszDest
0x1006b565  push    0Ch
0x1006b567  pop     edx
0x1006b568  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x1006b56d  cmp     ds:dword_1000B5B0[esi], 0
0x1006b574  jz      short loc_1006B57C
0x1006b576  inc     edi
0x1006b577  cmp     edi, 20h ; ' '
0x1006b57a  jb      short loc_1006B544
0x1006b57c  cvttsd2si eax, qword ptr [ebx+72h]
0x1006b581  mov     edi, [ebp+var_118]
0x1006b587  xor     edx, edx
0x1006b589  xor     [ebx+edx+42h], eax
0x1006b58d  lea     edx, [edx+4]
0x1006b590  lea     ecx, [edx+4]
0x1006b593  cmp     ecx, 28h ; '('
0x1006b596  jle     short loc_1006B589
0x1006b598  push    80h; unsigned int
0x1006b59d  push    [ebp+var_11C]; unsigned __int8 *
0x1006b5a3  lea     ecx, [ebp+var_114]; this
0x1006b5a9  call    ?Encrypt@Encryption@@QAEXPAEI@Z; Encryption::Encrypt(uchar *,uint)
0x1006b5ae  mov     ecx, [ebp+var_8]
0x1006b5b1  mov     eax, edi
0x1006b5b3  pop     edi
0x1006b5b4  pop     esi
0x1006b5b5  xor     ecx, ebp; StackCookie
0x1006b5b7  pop     ebx
0x1006b5b8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006b5bd  leave
0x1006b5be  retn    0Ch
```
