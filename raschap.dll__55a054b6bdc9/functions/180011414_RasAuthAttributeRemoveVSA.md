# RasAuthAttributeRemoveVSA

- ea: `0x180011414`
- end: `0x18001162d`
- name: `RasAuthAttributeRemoveVSA`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009dc0`

## callees

- `0x18000ab30`
- `0x18000abc0`
- `0x18000b610`
- `0x180011414`
- `0x180013b20`
- `0x180014610`
- `0x180024084`
- `0x180027010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800114a7`
- `rtutils!TracePrintfExA` at `0x1800115f7`
- `rtutils!TracePrintfExA` at `0x1800114a7`
- `rtutils!TracePrintfExA` at `0x1800115f7`

## string_xrefs

- `0x18001146d`: `RasAuthAttributeRemoveVSA: received NULL attributeArray, returning`
- `0x18001149b`: `RasAuthAttributeRemoveVSA: received NULL attributeArray, returning`
- `0x180011506`: `RasAuthAttributeRemoveVSA: RasAuthAttributeCreate failed`
- `0x180011521`: `RasAuthAttributeRemoveVSA: RasAuthAttributeCreate failed`
- `0x1800115a1`: `RasAuthAttributeRemoveVSA: Failed to copy existing attributes: 0x%x`
- `0x1800115e9`: `RasAuthAttributeRemoveVSA: Failed to copy existing attributes: 0x%x`

## pseudocode

```c
void *__fastcall RasAuthAttributeRemoveVSA(__int64 a1, _DWORD *a2)
{
  void *v3; // rdi
  __int64 v4; // rdx
  const wchar_t *v5; // r8
  unsigned int v6; // ebp
  int v7; // ecx
  unsigned int v8; // ecx
  int v9; // r14d
  int i; // ebp
  int v11; // r8d
  unsigned int v12; // eax
  size_t Size; // [rsp+20h] [rbp-848h]
  int v15; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-834h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( a2 )
  {
    v6 = 0;
    v7 = 0;
    if ( *a2 )
    {
      do
      {
        if ( a2[4 * v7] != 26 || *(_BYTE *)(*(_QWORD *)&a2[4 * v7 + 2] + 4LL) != 12 )
          ++v6;
        ++v7;
      }
      while ( a2[4 * v7] );
    }
    v3 = (void *)RasAuthAttributeCreate(v6);
    if ( v3 )
    {
      if ( v6 )
      {
        v8 = 0;
        v9 = 0;
        for ( i = 0; ; ++i )
        {
          v11 = a2[4 * i];
          if ( !v11 )
            break;
          if ( v11 != 26 || *(_BYTE *)(*(_QWORD *)&a2[4 * i + 2] + 4LL) != 12 )
          {
            LODWORD(Size) = a2[4 * i + 1];
            v12 = RasAuthAttributeInsert(v9++, (int)v3, v11, 0, Size, *(LPCWCH *)&a2[4 * i + 2]);
            v8 = v12;
            if ( v12 )
            {
              if ( gIsProtocolCommonTracingEnabled )
              {
                if ( qword_180033B68 )
                {
                  LOWORD(v15) = 0;
                  FormatRRASErrorString(
                    &v15,
                    L"RasAuthAttributeRemoveVSA: Failed to copy existing attributes: 0x%x",
                    v12);
                  ((void (__fastcall *)(__int64, __int64, int *))gProtocolCommonTemplateFunc)(
                    gProtocolCommonEtwContext,
                    qword_180033B68,
                    &v15);
                }
              }
              else if ( g_dwTraceId != -1 )
              {
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "RasAuthAttributeRemoveVSA: Failed to copy existing attributes: 0x%x",
                  v12);
              }
              goto LABEL_33;
            }
          }
        }
        if ( !v8 )
          return v3;
LABEL_33:
        RasAuthAttributeDestroy(v3);
        return 0;
      }
    }
    else
    {
      if ( gIsProtocolCommonTracingEnabled )
      {
        v4 = qword_180033B68;
        if ( !qword_180033B68 )
          return v3;
        v5 = L"RasAuthAttributeRemoveVSA: RasAuthAttributeCreate failed";
        goto LABEL_5;
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasAuthAttributeRemoveVSA: RasAuthAttributeCreate failed");
    }
  }
  else
  {
    v3 = 0;
    if ( gIsProtocolCommonTracingEnabled )
    {
      v4 = qword_180033B68;
      if ( qword_180033B68 )
      {
        v5 = L"RasAuthAttributeRemoveVSA: received NULL attributeArray, returning";
LABEL_5:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gProtocolCommonTemplateFunc)(
          gProtocolCommonEtwContext,
          v4,
          v5);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "RasAuthAttributeRemoveVSA: received NULL attributeArray, returning");
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180011414  push    rbx
0x180011416  push    rbp
0x180011417  push    rdi
0x180011418  push    r14
0x18001141a  sub     rsp, 848h
0x180011421  mov     rax, cs:__security_cookie
0x180011428  xor     rax, rsp
0x18001142b  mov     [rsp+868h+var_38], rax
0x180011433  mov     rbx, rdx
0x180011436  lea     rcx, [rsp+868h+var_834]; void *
0x18001143b  xor     eax, eax
0x18001143d  xor     edx, edx; Val
0x18001143f  mov     r8d, 7FCh; Size
0x180011445  mov     [rsp+868h+var_838], eax
0x180011449  call    memset_0
0x18001144e  test    rbx, rbx
0x180011451  jnz     short loc_1800114B2
0x180011453  xor     edi, edi
0x180011455  cmp     cs:gIsProtocolCommonTracingEnabled, edi
0x18001145b  jz      short loc_18001148C
0x18001145d  mov     rdx, cs:qword_180033B68
0x180011464  test    rdx, rdx
0x180011467  jz      loc_18001160D
0x18001146d  lea     r8, aRasauthattribu_4; "RasAuthAttributeRemoveVSA: received NUL"...
0x180011474  mov     rcx, cs:gProtocolCommonEtwContext
0x18001147b  mov     rax, cs:gProtocolCommonTemplateFunc
0x180011482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011487  jmp     loc_18001160D
0x18001148c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011492  cmp     ecx, 0FFFFFFFFh
0x180011495  jz      loc_18001160D
0x18001149b  lea     r8, szFormat; "RasAuthAttributeRemoveVSA: received NUL"...
0x1800114a2  mov     edx, 0Ch; dwFlags
0x1800114a7  call    cs:__imp_TracePrintfExA
0x1800114ad  jmp     loc_18001160D
0x1800114b2  xor     ebp, ebp
0x1800114b4  xor     ecx, ecx
0x1800114b6  cmp     [rbx], ecx
0x1800114b8  jz      short loc_1800114DF
0x1800114ba  mov     eax, ecx
0x1800114bc  add     rax, rax
0x1800114bf  cmp     dword ptr [rbx+rax*8], 1Ah
0x1800114c3  jnz     short loc_1800114D0
0x1800114c5  mov     rax, [rbx+rax*8+8]
0x1800114ca  cmp     byte ptr [rax+4], 0Ch
0x1800114ce  jz      short loc_1800114D2
0x1800114d0  inc     ebp
0x1800114d2  inc     ecx
0x1800114d4  mov     eax, ecx
0x1800114d6  add     rax, rax
0x1800114d9  cmp     dword ptr [rbx+rax*8], 0
0x1800114dd  jnz     short loc_1800114BA
0x1800114df  mov     ecx, ebp
0x1800114e1  call    RasAuthAttributeCreate
0x1800114e6  mov     rdi, rax
0x1800114e9  test    rax, rax
0x1800114ec  jnz     short loc_18001152D
0x1800114ee  cmp     cs:gIsProtocolCommonTracingEnabled, eax
0x1800114f4  jz      short loc_180011512
0x1800114f6  mov     rdx, cs:qword_180033B68
0x1800114fd  test    rdx, rdx
0x180011500  jz      loc_18001160D
0x180011506  lea     r8, aRasauthattribu_0; "RasAuthAttributeRemoveVSA: RasAuthAttri"...
0x18001150d  jmp     loc_180011474
0x180011512  mov     ecx, cs:g_dwTraceId
0x180011518  cmp     ecx, 0FFFFFFFFh
0x18001151b  jz      loc_18001160D
0x180011521  lea     r8, aRasauthattribu_1; "RasAuthAttributeRemoveVSA: RasAuthAttri"...
0x180011528  jmp     loc_1800114A2
0x18001152d  test    ebp, ebp
0x18001152f  jz      loc_18001160D
0x180011535  xor     ecx, ecx
0x180011537  xor     r14d, r14d
0x18001153a  xor     ebp, ebp
0x18001153c  mov     edx, ebp
0x18001153e  add     rdx, rdx
0x180011541  mov     r8d, [rbx+rdx*8]; int
0x180011545  test    r8d, r8d
0x180011548  jz      loc_1800115FF
0x18001154e  cmp     r8d, 1Ah
0x180011552  jnz     short loc_18001155F
0x180011554  mov     rax, [rbx+rdx*8+8]
0x180011559  cmp     byte ptr [rax+4], 0Ch
0x18001155d  jz      short loc_180011588
0x18001155f  mov     rax, [rbx+rdx*8+8]
0x180011564  xor     r9d, r9d; int
0x180011567  mov     [rsp+868h+lpWideCharStr], rax; lpWideCharStr
0x18001156c  mov     ecx, r14d; int
0x18001156f  mov     eax, [rbx+rdx*8+4]
0x180011573  mov     rdx, rdi; int
0x180011576  mov     dword ptr [rsp+868h+Size], eax; Size
0x18001157a  call    RasAuthAttributeInsert
0x18001157f  inc     r14d
0x180011582  mov     ecx, eax
0x180011584  test    eax, eax
0x180011586  jnz     short loc_18001158C
0x180011588  inc     ebp
0x18001158a  jmp     short loc_18001153C
0x18001158c  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180011593  jz      short loc_1800115DB
0x180011595  cmp     cs:qword_180033B68, 0
0x18001159d  jz      short loc_180011603
0x18001159f  xor     eax, eax
0x1800115a1  lea     rdx, aRasauthattribu; "RasAuthAttributeRemoveVSA: Failed to co"...
0x1800115a8  mov     r8d, ecx
0x1800115ab  mov     word ptr [rsp+868h+var_838], ax
0x1800115b0  lea     rcx, [rsp+868h+var_838]
0x1800115b5  call    FormatRRASErrorString
0x1800115ba  mov     rdx, cs:qword_180033B68
0x1800115c1  lea     r8, [rsp+868h+var_838]
0x1800115c6  mov     rcx, cs:gProtocolCommonEtwContext
0x1800115cd  mov     rax, cs:gProtocolCommonTemplateFunc
0x1800115d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d9  jmp     short loc_180011603
0x1800115db  mov     eax, cs:g_dwTraceId
0x1800115e1  cmp     eax, 0FFFFFFFFh
0x1800115e4  jz      short loc_180011603
0x1800115e6  mov     r9d, ecx
0x1800115e9  lea     r8, aRasauthattribu_2; "RasAuthAttributeRemoveVSA: Failed to co"...
0x1800115f0  mov     ecx, eax; dwTraceID
0x1800115f2  mov     edx, 0Ch; dwFlags
0x1800115f7  call    cs:__imp_TracePrintfExA
0x1800115fd  jmp     short loc_180011603
0x1800115ff  test    ecx, ecx
0x180011601  jz      short loc_18001160D
0x180011603  mov     rcx, rdi; hMem
0x180011606  call    RasAuthAttributeDestroy
0x18001160b  xor     edi, edi
0x18001160d  mov     rax, rdi
0x180011610  mov     rcx, [rsp+868h+var_38]
0x180011618  xor     rcx, rsp; StackCookie
0x18001161b  call    __security_check_cookie
0x180011620  add     rsp, 848h
0x180011627  pop     r14
0x180011629  pop     rdi
0x18001162a  pop     rbp
0x18001162b  pop     rbx
0x18001162c  retn
```
