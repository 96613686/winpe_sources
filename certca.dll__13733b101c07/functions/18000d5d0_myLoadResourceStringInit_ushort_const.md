# myLoadResourceStringInit(ushort const *)

- ea: `0x18000d5d0`
- end: `0x18000d999`
- name: `?myLoadResourceStringInit@@YAXPEBG@Z`
- size: `969`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011240`

## callees

- `0x180008610`
- `0x18000d110`
- `0x18000d5d0`
- `0x18000dda0`
- `0x180013a86`
- `0x18001e884`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000d613`
- `msvcrt!wcsrchr` at `0x18000d613`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d75b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d764`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d75b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d764`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d645`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d645`

## string_xrefs

- `0x18000d5f6`: `certca.dll`

## pseudocode

```c
void __fastcall myLoadResourceStringInit(unsigned __int16 *a1)
{
  const wchar_t *v1; // rbx
  wchar_t *v2; // rax
  __int64 v3; // rdi
  int ProcessName; // eax
  int v5; // r8d
  unsigned int v6; // edx
  __int64 v7; // rax
  bool v8; // zf
  SIZE_T v9; // rbp
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  const WCHAR *v12; // rbx
  __int64 v13; // r10
  unsigned __int64 v14; // rdi
  const WCHAR *v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  WCHAR *v21; // r8
  WCHAR *v22; // rdx
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  const WCHAR *v26; // rax
  unsigned __int64 v27; // r9
  const WCHAR *v28; // r8
  __int64 v29; // rcx
  WCHAR *v30; // rax
  unsigned __int64 j; // rdx
  WCHAR *v32; // rcx
  unsigned __int64 v33; // rcx
  const WCHAR *v34; // rax
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  const wchar_t *v37; // rdx
  WCHAR *i; // rax
  int v39; // edx
  int v40; // eax
  int v41; // ebx
  unsigned int v42; // edx
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  hMem = a1;
  if ( !s_pwszMuiModuleName )
  {
    v1 = L"certca.dll";
    hMem = 0;
    v2 = wcsrchr(L"certca.dll", 0x2Eu);
    v3 = -1;
    if ( !v2 || CompareStringW(0x7Fu, 1u, v2, -1, L".exe", -1) != 2 )
      goto LABEL_8;
    ProcessName = myGetProcessName((unsigned __int16 **)&hMem);
    if ( ProcessName )
    {
      v5 = ProcessName;
      v6 = 7340471;
    }
    else
    {
      if ( HasExeSuffix((const unsigned __int16 *)hMem)
        || (v40 = myJoinStrings(L".exe", v39, 0, (unsigned __int16 **)&hMem)) == 0 )
      {
        v1 = (const wchar_t *)hMem;
        if ( !hMem )
        {
          v11 = 0;
          v41 = -2147467261;
          v42 = 101908938;
          goto LABEL_66;
        }
LABEL_8:
        v7 = -1;
        do
          v8 = v1[++v7] == 0;
        while ( !v8 );
        v9 = 2 * v7 + 2;
        v10 = (WCHAR *)LocalAlloc(0, v9);
        v11 = v10;
        if ( v10 )
        {
          memcpy_0(v10, v1, v9);
          do
            ++v3;
          while ( v11[v3] );
          v12 = (const WCHAR *)LocalAlloc(0, 2 * v3 + 10);
          if ( !v12 )
          {
            CSPrintErrorLineFileData2(0, 0x71401CAu, -2147024882, 0);
            CSPrintErrorLineFileData2(0, 0x8101B7u, -2147024882, 0);
            goto LABEL_24;
          }
          v13 = 2147483646;
          *v12 = 0;
          v14 = v3 + 5;
          if ( !v14 )
            goto LABEL_35;
          if ( v14 > 0x7FFFFFFF )
            goto LABEL_23;
          v15 = v12;
          v16 = v14;
          while ( *v15 )
          {
            ++v15;
            if ( !--v16 )
            {
              v17 = 0;
              goto LABEL_27;
            }
          }
          v17 = v14 - v16;
LABEL_27:
          if ( v16 )
          {
            v19 = 2147483646;
            v20 = v14 - v17;
            v8 = v14 == v17;
            v21 = v11;
            v22 = (WCHAR *)&v12[v17];
            if ( !v8 )
            {
              do
              {
                if ( !v19 )
                  break;
                if ( !*v21 )
                  break;
                *v22++ = *v21++;
                --v19;
                --v20;
              }
              while ( v20 );
            }
            v23 = v22 - 1;
            if ( v20 )
              v23 = v22;
            v24 = v14;
            *v23 = 0;
            v25 = v14;
          }
          else
          {
LABEL_35:
            v24 = v14;
            if ( !v14 )
            {
LABEL_48:
              v33 = v14;
              if ( v14 - 1 <= 0x7FFFFFFE )
              {
LABEL_49:
                v34 = v12;
                do
                {
                  if ( !*v34 )
                    break;
                  ++v34;
                  --v14;
                }
                while ( v14 );
                if ( v14 )
                  v35 = v33 - v14;
                else
                  v35 = 0;
                if ( v14 )
                {
                  v36 = v33 - v35;
                  v37 = L".mui";
                  for ( i = (WCHAR *)&v12[v35]; v36; --v36 )
                  {
                    if ( !v13 )
                      break;
                    if ( !*v37 )
                      break;
                    *i++ = *v37++;
                    --v13;
                  }
                  v18 = i - 1;
                  if ( v36 )
                    v18 = i;
                  *v18 = 0;
                }
              }
LABEL_23:
              LocalFree(v11);
              v11 = 0;
              s_pwszMuiModuleName = v12;
LABEL_24:
              LocalFree(hMem);
              LocalFree(v11);
              return;
            }
            v25 = v14;
          }
          v26 = v12;
          do
          {
            if ( !*v26 )
              break;
            ++v26;
            --v25;
          }
          while ( v25 );
          v27 = v24 - v25;
          if ( v25 )
          {
            v28 = &Class;
            v29 = 2147483646;
            v30 = (WCHAR *)&v12[v27];
            for ( j = v24 - v27; j; --j )
            {
              if ( !v29 )
                break;
              if ( !*v28 )
                break;
              *v30++ = *v28++;
              --v29;
            }
            v32 = v30 - 1;
            if ( j )
              v32 = v30;
            *v32 = 0;
            v33 = v14;
            goto LABEL_49;
          }
          goto LABEL_48;
        }
        v41 = -2147024882;
        v42 = 102367690;
LABEL_66:
        CSPrintErrorLineFileData2(0, v42, v41, 0);
        CSPrintErrorLineFileData2(0, 0x7D01B7u, v41, 0);
        goto LABEL_24;
      }
      v5 = v40;
      v6 = 7602615;
    }
    CSPrintErrorLineFileData2(0, v6, v5, 0);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x18000d5d0  mov     [rsp+hMem], rcx
0x18000d5d5  sub     rsp, 38h
0x18000d5d9  cmp     cs:?s_pwszMuiModuleName@@3PEAGEA, 0; ushort * s_pwszMuiModuleName
0x18000d5e1  jnz     loc_18000D77E
0x18000d5e7  mov     [rsp+38h+arg_8], rbx
0x18000d5ec  mov     edx, 2Eh ; '.'; Ch
0x18000d5f1  mov     [rsp+38h+arg_18], rsi
0x18000d5f6  lea     rbx, aCertcaDll_0; "certca.dll"
0x18000d5fd  mov     rcx, rbx; Str
0x18000d600  mov     [rsp+38h+var_8], rdi
0x18000d605  mov     [rsp+38h+arg_10], rbp
0x18000d60a  mov     [rsp+38h+hMem], 0
0x18000d613  call    cs:__imp_wcsrchr
0x18000d619  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000d620  test    rax, rax
0x18000d623  jz      short loc_18000D684
0x18000d625  lea     rsi, aExe; ".exe"
0x18000d62c  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18000d630  mov     r9d, edi; cchCount1
0x18000d633  mov     [rsp+38h+lpString2], rsi; lpString2
0x18000d638  mov     r8, rax; lpString1
0x18000d63b  mov     edx, 1; dwCmpFlags
0x18000d640  mov     ecx, 7Fh; Locale
0x18000d645  call    cs:__imp_CompareStringW
0x18000d64b  cmp     eax, 2
0x18000d64e  jnz     short loc_18000D684
0x18000d650  lea     rcx, [rsp+38h+hMem]; unsigned __int16 **
0x18000d655  call    ?myGetProcessName@@YAJPEAPEAG@Z; myGetProcessName(ushort * *)
0x18000d65a  test    eax, eax
0x18000d65c  jz      loc_18000D8F5
0x18000d662  xor     r9d, r9d; int
0x18000d665  mov     r8d, eax; int
0x18000d668  mov     edx, 7001B7h; unsigned int
0x18000d66d  xor     ecx, ecx; unsigned __int16 *
0x18000d66f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d674  jmp     short loc_18000D684
0x18000d676  mov     rbx, [rsp+38h+hMem]
0x18000d67b  test    rbx, rbx
0x18000d67e  jz      loc_18000D92F
0x18000d684  mov     rax, rdi
0x18000d687  nop     word ptr [rax+rax+00000000h]
0x18000d690  cmp     word ptr [rbx+rax*2+2], 0
0x18000d696  lea     rax, [rax+1]
0x18000d69a  jnz     short loc_18000D690
0x18000d69c  lea     rbp, ds:2[rax*2]
0x18000d6a4  xor     ecx, ecx; uFlags
0x18000d6a6  mov     rdx, rbp; uBytes
0x18000d6a9  call    cs:__imp_LocalAlloc
0x18000d6af  mov     rsi, rax
0x18000d6b2  test    rax, rax
0x18000d6b5  jz      loc_18000D93D
0x18000d6bb  mov     r8, rbp; Size
0x18000d6be  mov     rdx, rbx; Src
0x18000d6c1  mov     rcx, rax; void *
0x18000d6c4  call    memcpy_0
0x18000d6c9  nop     dword ptr [rax+00000000h]
0x18000d6d0  inc     rdi
0x18000d6d3  cmp     word ptr [rsi+rdi*2], 0
0x18000d6d8  jnz     short loc_18000D6D0
0x18000d6da  lea     rdx, ds:0Ah[rdi*2]; uBytes
0x18000d6e2  xor     ecx, ecx; uFlags
0x18000d6e4  call    cs:__imp_LocalAlloc
0x18000d6ea  mov     rbx, rax
0x18000d6ed  test    rax, rax
0x18000d6f0  jz      loc_18000D96B
0x18000d6f6  xor     eax, eax
0x18000d6f8  mov     r10d, 7FFFFFFEh
0x18000d6fe  mov     [rbx], ax
0x18000d701  add     rdi, 5
0x18000d705  jz      loc_18000D7DC
0x18000d70b  cmp     rdi, 7FFFFFFFh
0x18000d712  ja      short loc_18000D744
0x18000d714  mov     rax, rbx
0x18000d717  mov     rcx, rdi
0x18000d71a  nop     word ptr [rax+rax+00h]
0x18000d720  cmp     word ptr [rax], 0
0x18000d724  jz      short loc_18000D783
0x18000d726  add     rax, 2
0x18000d72a  sub     rcx, 1
0x18000d72e  jnz     short loc_18000D720
0x18000d730  xor     edx, edx
0x18000d732  jmp     short loc_18000D789
0x18000d734  test    rcx, rcx
0x18000d737  lea     rdx, [rax-2]
0x18000d73b  cmovnz  rdx, rax
0x18000d73f  xor     eax, eax
0x18000d741  mov     [rdx], ax
0x18000d744  mov     rcx, rsi; hMem
0x18000d747  call    cs:__imp_LocalFree
0x18000d74d  xor     esi, esi
0x18000d74f  mov     cs:?s_pwszMuiModuleName@@3PEAGEA, rbx; ushort * s_pwszMuiModuleName
0x18000d756  mov     rcx, [rsp+38h+hMem]; hMem
0x18000d75b  call    cs:__imp_LocalFree
0x18000d761  mov     rcx, rsi; hMem
0x18000d764  call    cs:__imp_LocalFree
0x18000d76a  mov     rdi, [rsp+38h+var_8]
0x18000d76f  mov     rsi, [rsp+38h+arg_18]
0x18000d774  mov     rbp, [rsp+38h+arg_10]
0x18000d779  mov     rbx, [rsp+38h+arg_8]
0x18000d77e  add     rsp, 38h
0x18000d782  retn
0x18000d783  mov     rdx, rdi
0x18000d786  sub     rdx, rcx
0x18000d789  test    rcx, rcx
0x18000d78c  jz      short loc_18000D7DC
0x18000d78e  mov     rax, rdi
0x18000d791  mov     rcx, r10
0x18000d794  sub     rax, rdx
0x18000d797  mov     r8, rsi
0x18000d79a  lea     rdx, [rbx+rdx*2]
0x18000d79e  jz      short loc_18000D7C4
0x18000d7a0  test    rcx, rcx
0x18000d7a3  jz      short loc_18000D7C4
0x18000d7a5  movzx   r9d, word ptr [r8]
0x18000d7a9  test    r9w, r9w
0x18000d7ad  jz      short loc_18000D7C4
0x18000d7af  mov     [rdx], r9w
0x18000d7b3  add     r8, 2
0x18000d7b7  add     rdx, 2
0x18000d7bb  dec     rcx
0x18000d7be  sub     rax, 1
0x18000d7c2  jnz     short loc_18000D7A0
0x18000d7c4  test    rax, rax
0x18000d7c7  lea     rcx, [rdx-2]
0x18000d7cb  cmovnz  rcx, rdx
0x18000d7cf  xor     eax, eax
0x18000d7d1  mov     rdx, rdi
0x18000d7d4  mov     [rcx], ax
0x18000d7d7  mov     rcx, rdi
0x18000d7da  jmp     short loc_18000D7F8
0x18000d7dc  mov     rdx, rdi
0x18000d7df  test    rdi, rdi
0x18000d7e2  jz      loc_18000D86D
0x18000d7e8  cmp     rdx, 7FFFFFFFh
0x18000d7ef  ja      loc_18000D744
0x18000d7f5  mov     rcx, rdx
0x18000d7f8  mov     rax, rbx
0x18000d7fb  nop     dword ptr [rax+rax+00h]
0x18000d800  cmp     word ptr [rax], 0
0x18000d804  jz      short loc_18000D810
0x18000d806  add     rax, 2
0x18000d80a  sub     rcx, 1
0x18000d80e  jnz     short loc_18000D800
0x18000d810  xor     eax, eax
0x18000d812  mov     r9, rdx
0x18000d815  sub     r9, rcx
0x18000d818  test    rcx, rcx
0x18000d81b  cmovz   r9, rax
0x18000d81f  jz      short loc_18000D86D
0x18000d821  lea     r8, Class
0x18000d828  mov     rcx, r10
0x18000d82b  lea     rax, [rbx+r9*2]
0x18000d82f  sub     rdx, r9
0x18000d832  jz      short loc_18000D858
0x18000d834  test    rcx, rcx
0x18000d837  jz      short loc_18000D858
0x18000d839  movzx   r9d, word ptr [r8]
0x18000d83d  test    r9w, r9w
0x18000d841  jz      short loc_18000D858
0x18000d843  mov     [rax], r9w
0x18000d847  add     r8, 2
0x18000d84b  add     rax, 2
0x18000d84f  dec     rcx
0x18000d852  sub     rdx, 1
0x18000d856  jnz     short loc_18000D834
0x18000d858  test    rdx, rdx
0x18000d85b  lea     rcx, [rax-2]
0x18000d85f  cmovnz  rcx, rax
0x18000d863  xor     eax, eax
0x18000d865  mov     [rcx], ax
0x18000d868  mov     rcx, rdi
0x18000d86b  jmp     short loc_18000D87D
0x18000d86d  lea     rax, [rdi-1]
0x18000d871  mov     rcx, rdi
0x18000d874  cmp     rax, r10
0x18000d877  ja      loc_18000D744
0x18000d87d  mov     rax, rbx
0x18000d880  cmp     word ptr [rax], 0
0x18000d884  jz      short loc_18000D890
0x18000d886  add     rax, 2
0x18000d88a  sub     rdi, 1
0x18000d88e  jnz     short loc_18000D880
0x18000d890  test    rdi, rdi
0x18000d893  jz      short loc_18000D8F1
0x18000d895  mov     rax, rcx
0x18000d898  sub     rax, rdi
0x18000d89b  test    rdi, rdi
0x18000d89e  jz      loc_18000D744
0x18000d8a4  sub     rcx, rax
0x18000d8a7  lea     rdx, aMui_0; ".mui"
0x18000d8ae  lea     rax, [rbx+rax*2]
0x18000d8b2  jz      loc_18000D734
0x18000d8b8  nop     dword ptr [rax+rax+00000000h]
0x18000d8c0  test    r10, r10
0x18000d8c3  jz      loc_18000D734
0x18000d8c9  movzx   r8d, word ptr [rdx]
0x18000d8cd  test    r8w, r8w
0x18000d8d1  jz      loc_18000D734
0x18000d8d7  mov     [rax], r8w
0x18000d8db  add     rdx, 2
0x18000d8df  add     rax, 2
0x18000d8e3  dec     r10
0x18000d8e6  sub     rcx, 1
0x18000d8ea  jnz     short loc_18000D8C0
0x18000d8ec  jmp     loc_18000D734
0x18000d8f1  xor     eax, eax
0x18000d8f3  jmp     short loc_18000D89B
0x18000d8f5  mov     rcx, [rsp+38h+hMem]; unsigned __int16 *
0x18000d8fa  call    ?HasExeSuffix@@YA_NPEBG@Z; HasExeSuffix(ushort const *)
0x18000d8ff  test    al, al
0x18000d901  jnz     loc_18000D676
0x18000d907  lea     r9, [rsp+38h+hMem]; unsigned __int16 **
0x18000d90c  xor     r8d, r8d; unsigned __int16 *
0x18000d90f  mov     rcx, rsi; unsigned __int16 *
0x18000d912  call    ?myJoinStrings@@YAJPEBGH0PEAPEAG@Z; myJoinStrings(ushort const *,int,ushort const *,ushort * *)
0x18000d917  test    eax, eax
0x18000d919  jz      loc_18000D676
0x18000d91f  xor     r9d, r9d
0x18000d922  mov     r8d, eax
0x18000d925  mov     edx, 7401B7h
0x18000d92a  jmp     loc_18000D66D
0x18000d92f  xor     esi, esi
0x18000d931  mov     ebx, 80004003h
0x18000d936  mov     edx, 61301CAh
0x18000d93b  jmp     short loc_18000D947
0x18000d93d  mov     ebx, 8007000Eh
0x18000d942  mov     edx, 61A01CAh; unsigned int
0x18000d947  xor     ecx, ecx; unsigned __int16 *
0x18000d949  xor     r9d, r9d; int
0x18000d94c  mov     r8d, ebx; int
0x18000d94f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d954  xor     r9d, r9d; int
0x18000d957  mov     r8d, ebx; int
0x18000d95a  mov     edx, 7D01B7h; unsigned int
0x18000d95f  xor     ecx, ecx; unsigned __int16 *
0x18000d961  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d966  jmp     loc_18000D756
0x18000d96b  mov     ebx, 8007000Eh
0x18000d970  xor     r9d, r9d; int
0x18000d973  mov     r8d, ebx; int
0x18000d976  mov     edx, 71401CAh; unsigned int
0x18000d97b  xor     ecx, ecx; unsigned __int16 *
0x18000d97d  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d982  xor     r9d, r9d; int
0x18000d985  mov     r8d, ebx; int
0x18000d988  mov     edx, 8101B7h; unsigned int
0x18000d98d  xor     ecx, ecx; unsigned __int16 *
0x18000d98f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000d994  jmp     loc_18000D756
```
