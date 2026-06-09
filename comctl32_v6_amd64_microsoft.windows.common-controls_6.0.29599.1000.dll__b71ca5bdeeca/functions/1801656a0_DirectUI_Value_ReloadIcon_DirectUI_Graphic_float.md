# DirectUI::Value::ReloadIcon(DirectUI::Graphic *,float)

- ea: `0x1801656a0`
- end: `0x180165863`
- name: `?ReloadIcon@Value@DirectUI@@CAPEAUHICON__@@PEAUGraphic@2@M@Z`
- size: `451`
- prototype: `HICON __fastcall(struct DirectUI::Graphic *, float)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180164aa8`
- `0x180165390`

## callees

- `0x180114e74`
- `0x1801656a0`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801657a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801657b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801657a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801657b2`
- `GDI32!DeleteObject` at `0x18016582d`
- `GDI32!DeleteObject` at `0x180165837`
- `GDI32!DeleteObject` at `0x18016582d`
- `GDI32!DeleteObject` at `0x180165837`
- `GDI32!GetObjectW` at `0x1801657fb`
- `GDI32!GetObjectW` at `0x18016580f`
- `GDI32!GetObjectW` at `0x1801657fb`
- `GDI32!GetObjectW` at `0x18016580f`
- `USER32!LoadImageW` at `0x180165799`
- `USER32!LoadImageW` at `0x180165799`
- `USER32!DestroyIcon` at `0x1801656dc`
- `USER32!DestroyIcon` at `0x1801656dc`
- `USER32!GetIconInfo` at `0x1801657d7`
- `USER32!GetIconInfo` at `0x1801657d7`

## pseudocode

```c
HICON __fastcall DirectUI::Value::ReloadIcon(struct DirectUI::Graphic *a1, float a2)
{
  HICON v3; // rcx
  HICON result; // rax
  bool v5; // zf
  int v6; // edi
  int cy; // r8d
  ICONINFO piconinfo; // [rsp+30h] [rbp-50h] BYREF
  _OWORD pv[2]; // [rsp+50h] [rbp-30h] BYREF
  HICON v10; // [rsp+90h] [rbp+10h] BYREF

  v3 = *(HICON *)a1;
  if ( v3 )
  {
    if ( *((float *)a1 + 15) == a2 )
      return v3;
    DestroyIcon(v3);
    *(_QWORD *)a1 = 0;
  }
  v5 = (*((_BYTE *)a1 + 56) & 2) == 0;
  v6 = *((_DWORD *)a1 + 12);
  v10 = 0;
  if ( !v5 )
    v6 = (int)floorf((float)((float)v6 * a2) + 0.5);
  cy = *((_DWORD *)a1 + 13);
  if ( (*((_BYTE *)a1 + 56) & 1) != 0 )
    cy = (int)floorf((float)((float)cy * a2) + 0.5);
  if ( DirectUI::g_pfnLoadIconWithScaleDown )
  {
    if ( DirectUI::g_pfnLoadIconWithScaleDown(
           *((struct HINSTANCE__ **)a1 + 4),
           *((const unsigned __int16 **)a1 + 5),
           v6,
           cy,
           &v10) < 0 )
    {
      result = 0;
      v10 = 0;
      goto LABEL_16;
    }
LABEL_15:
    result = v10;
LABEL_16:
    if ( !result )
      return result;
    goto LABEL_17;
  }
  result = (HICON)LoadImageW(
                    *((HINSTANCE *)a1 + 4),
                    *((LPCWSTR *)a1 + 5),
                    1u,
                    v6,
                    cy,
                    *((_QWORD *)a1 + 4) == 0 ? 0x10 : 0);
  v10 = result;
  if ( !result )
  {
    if ( GetLastError() )
      GetLastError();
    goto LABEL_15;
  }
LABEL_17:
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( GetIconInfo(result, &piconinfo) )
  {
    memset(pv, 0, sizeof(pv));
    if ( GetObjectW(piconinfo.hbmColor, 32, pv) || GetObjectW(piconinfo.hbmMask, 32, pv) )
    {
      *((_WORD *)a1 + 8) = WORD2(pv[0]);
      *((_WORD *)a1 + 9) = WORD4(pv[0]);
    }
    DeleteObject(piconinfo.hbmMask);
    DeleteObject(piconinfo.hbmColor);
  }
  result = v10;
  *(_QWORD *)a1 = v10;
  *((float *)a1 + 15) = a2;
  return result;
}

```

## disassembly

```asm
0x1801656a0  mov     [rsp-8+arg_8], rbx
0x1801656a5  mov     [rsp-8+arg_10], rdi
0x1801656aa  push    rbp
0x1801656ab  mov     rbp, rsp
0x1801656ae  sub     rsp, 80h
0x1801656b5  mov     rbx, rcx
0x1801656b8  movaps  [rsp+80h+var_10], xmm6
0x1801656bd  mov     rcx, [rcx]; hIcon
0x1801656c0  movaps  xmm6, xmm1
0x1801656c3  test    rcx, rcx
0x1801656c6  jz      short loc_1801656E9
0x1801656c8  movss   xmm0, dword ptr [rbx+3Ch]
0x1801656cd  ucomiss xmm0, xmm6
0x1801656d0  jp      short loc_1801656DC
0x1801656d2  jnz     short loc_1801656DC
0x1801656d4  mov     rax, rcx
0x1801656d7  jmp     loc_180165849
0x1801656dc  call    cs:__imp_DestroyIcon
0x1801656e2  mov     qword ptr [rbx], 0
0x1801656e9  test    byte ptr [rbx+38h], 2
0x1801656ed  mov     edi, [rbx+30h]
0x1801656f0  mov     [rbp+arg_0], 0
0x1801656f8  jz      short loc_180165716
0x1801656fa  movd    xmm0, edi
0x1801656fe  cvtdq2ps xmm0, xmm0
0x180165701  mulss   xmm0, xmm6
0x180165705  addss   xmm0, cs:__real@3f000000; X
0x18016570d  call    floorf
0x180165712  cvttss2si edi, xmm0
0x180165716  test    byte ptr [rbx+38h], 1
0x18016571a  mov     r8d, [rbx+34h]
0x18016571e  jz      short loc_18016573E
0x180165720  movd    xmm0, r8d
0x180165725  cvtdq2ps xmm0, xmm0
0x180165728  mulss   xmm0, xmm6
0x18016572c  addss   xmm0, cs:__real@3f000000; X
0x180165734  call    floorf
0x180165739  cvttss2si r8d, xmm0
0x18016573e  mov     rax, cs:?g_pfnLoadIconWithScaleDown@DirectUI@@3P6AJPEAUHINSTANCE__@@PEBGHHPEAPEAUHICON__@@@ZEA; long (*DirectUI::g_pfnLoadIconWithScaleDown)(HINSTANCE__ *,ushort const *,int,int,HICON__ * *)
0x180165745  test    rax, rax
0x180165748  jz      short loc_180165772
0x18016574a  mov     rdx, [rbx+28h]
0x18016574e  lea     rcx, [rbp+arg_0]
0x180165752  mov     qword ptr [rsp+80h+cy], rcx
0x180165757  mov     r9d, r8d
0x18016575a  mov     rcx, [rbx+20h]
0x18016575e  mov     r8d, edi
0x180165761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165766  test    eax, eax
0x180165768  jns     short loc_1801657B8
0x18016576a  xor     eax, eax
0x18016576c  mov     [rbp+arg_0], rax
0x180165770  jmp     short loc_1801657BC
0x180165772  mov     rcx, [rbx+20h]; hInst
0x180165776  mov     r9d, edi; cx
0x180165779  mov     rax, rcx
0x18016577c  neg     rax
0x18016577f  sbb     edx, edx
0x180165781  not     edx
0x180165783  and     edx, 10h
0x180165786  mov     [rsp+80h+fuLoad], edx; fuLoad
0x18016578a  mov     rdx, [rbx+28h]; name
0x18016578e  mov     [rsp+80h+cy], r8d; cy
0x180165793  mov     r8d, 1; type
0x180165799  call    cs:__imp_LoadImageW
0x18016579f  mov     [rbp+arg_0], rax
0x1801657a3  test    rax, rax
0x1801657a6  jnz     short loc_1801657C5
0x1801657a8  call    cs:__imp_GetLastError
0x1801657ae  test    eax, eax
0x1801657b0  jz      short loc_1801657B8
0x1801657b2  call    cs:__imp_GetLastError
0x1801657b8  mov     rax, [rbp+arg_0]
0x1801657bc  test    rax, rax
0x1801657bf  jz      loc_180165849
0x1801657c5  xorps   xmm0, xmm0
0x1801657c8  lea     rdx, [rbp+piconinfo]; piconinfo
0x1801657cc  mov     rcx, rax; hIcon
0x1801657cf  movups  xmmword ptr [rbp+piconinfo.fIcon], xmm0
0x1801657d3  movups  xmmword ptr [rbp+piconinfo.hbmMask], xmm0
0x1801657d7  call    cs:__imp_GetIconInfo
0x1801657dd  test    eax, eax
0x1801657df  jz      short loc_18016583D
0x1801657e1  mov     rcx, [rbp+piconinfo.hbmColor]; h
0x1801657e5  lea     r8, [rbp+pv]; pv
0x1801657e9  xorps   xmm0, xmm0
0x1801657ec  mov     edi, 20h ; ' '
0x1801657f1  mov     edx, edi; c
0x1801657f3  movups  [rbp+pv], xmm0
0x1801657f7  movups  [rbp+var_20], xmm0
0x1801657fb  call    cs:__imp_GetObjectW
0x180165801  test    eax, eax
0x180165803  jnz     short loc_180165819
0x180165805  mov     rcx, [rbp+piconinfo.hbmMask]; h
0x180165809  lea     r8, [rbp+pv]; pv
0x18016580d  mov     edx, edi; c
0x18016580f  call    cs:__imp_GetObjectW
0x180165815  test    eax, eax
0x180165817  jz      short loc_180165829
0x180165819  movzx   eax, word ptr [rbp+pv+4]
0x18016581d  mov     [rbx+10h], ax
0x180165821  movzx   eax, word ptr [rbp+pv+8]
0x180165825  mov     [rbx+12h], ax
0x180165829  mov     rcx, [rbp+piconinfo.hbmMask]; ho
0x18016582d  call    cs:__imp_DeleteObject
0x180165833  mov     rcx, [rbp+piconinfo.hbmColor]; ho
0x180165837  call    cs:__imp_DeleteObject
0x18016583d  mov     rax, [rbp+arg_0]
0x180165841  mov     [rbx], rax
0x180165844  movss   dword ptr [rbx+3Ch], xmm6
0x180165849  movaps  xmm6, [rsp+80h+var_10]
0x18016584e  lea     r11, [rsp+80h+var_s0]
0x180165856  mov     rbx, [r11+18h]
0x18016585a  mov     rdi, [r11+20h]
0x18016585e  mov     rsp, r11
0x180165861  pop     rbp
0x180165862  retn
```
