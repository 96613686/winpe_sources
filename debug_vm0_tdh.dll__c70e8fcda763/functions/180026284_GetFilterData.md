# GetFilterData

- ea: `0x180026284`
- end: `0x180026406`
- name: `GetFilterData`
- size: `386`
- prototype: `int __fastcall(PublisherManifestResource *this, __int64, HINSTANCE, __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002658c`

## callees

- `0x18000adf0`
- `0x18000b120`
- `0x18000c0e8`
- `0x18000c300`
- `0x180026284`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002634f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002634f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002633c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002633c`

## pseudocode

```c
int __fastcall GetFilterData(PublisherManifestResource *this, __int64 a2, HINSTANCE a3, __int64 a4, int *a5)
{
  DWORD v6; // edx
  int v8; // edi
  _DWORD *v10; // rbx
  int result; // eax
  const struct TemplateResource *v12; // rdx
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rax
  __int64 v16; // r12
  __int64 i; // rbx
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  unsigned int *v20; // [rsp+20h] [rbp-71h]
  __int128 v21; // [rsp+30h] [rbp-61h] BYREF
  __int128 v22; // [rsp+40h] [rbp-51h]
  __int128 v23; // [rsp+50h] [rbp-41h]
  __int64 v24; // [rsp+60h] [rbp-31h]
  __int128 v25; // [rsp+68h] [rbp-29h] BYREF
  __int128 v26; // [rsp+78h] [rbp-19h]
  __int128 v27; // [rsp+88h] [rbp-9h]
  __int64 v28; // [rsp+98h] [rbp+7h]

  v28 = 0;
  v24 = 0;
  v6 = *(_DWORD *)(a2 + 16);
  v8 = 40;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( v6 != -1 )
  {
    v10 = (_DWORD *)(a4 + 64);
    result = TdhpGetResourceName(
               a3,
               v6,
               0,
               (wchar_t **)(a4 + 56),
               (unsigned int *)(a4 + 64),
               (unsigned __int8 *)(a4 + 68));
    if ( result )
      return result;
    v8 = *v10 + 40;
  }
  v12 = *(const struct TemplateResource **)(a2 + 24);
  v13 = 0;
  if ( v12 )
  {
    result = PublisherManifestResource::GetTemplateResource(this, v12, (struct TemplateResourceData *)&v25);
    if ( result )
      return result;
    v13 = v26;
    if ( (_DWORD)v26 )
      v8 = v8 + 24 * v26 - 24;
  }
  ProcessHeap = GetProcessHeap();
  v15 = HeapAlloc(ProcessHeap, 8u, 88LL * v13);
  *(_QWORD *)(a4 + 48) = v15;
  if ( !v15 )
    return 8;
  v16 = *((_QWORD *)&v26 + 1);
  for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
  {
    result = PublisherManifestResource::GetTypeResource(
               this,
               (const struct TemplateResourceData *)&v25,
               (const struct TypeResource *)(v16 + 20 * i),
               (struct TypeResourceData *)&v21);
    if ( result )
      return result;
    v16 = *((_QWORD *)&v26 + 1);
    v18 = v22;
    v20 = (unsigned int *)(*(_QWORD *)(a4 + 48) + 88LL * (unsigned int)i);
    *(_OWORD *)v20 = v21;
    v19 = v23;
    *((_OWORD *)v20 + 1) = v18;
    *(_QWORD *)&v18 = v24;
    *((_OWORD *)v20 + 2) = v19;
    *((_QWORD *)v20 + 6) = v18;
    result = GetEventPropertyInfoManifest(this, (__int64)v20);
    if ( result )
      return result;
  }
  *a5 = v8;
  return 0;
}

```

## disassembly

```asm
0x180026284  push    rbp
0x180026286  push    rbx
0x180026287  push    rsi
0x180026288  push    rdi
0x180026289  push    r12
0x18002628b  push    r13
0x18002628d  push    r14
0x18002628f  push    r15
0x180026291  lea     rbp, [rsp-17h]
0x180026296  sub     rsp, 0A8h
0x18002629d  xor     eax, eax
0x18002629f  xorps   xmm0, xmm0
0x1800262a2  xorps   xmm1, xmm1
0x1800262a5  mov     [rbp+4Fh+var_48], rax
0x1800262a9  mov     r15, rdx
0x1800262ac  mov     [rbp+4Fh+var_80], rax
0x1800262b0  mov     edx, [rdx+10h]; dwMessageId
0x1800262b3  mov     r14, r9
0x1800262b6  lea     edi, [rax+28h]
0x1800262b9  mov     r10, r8
0x1800262bc  mov     r13, rcx
0x1800262bf  movups  [rbp+4Fh+var_78], xmm0
0x1800262c3  movups  [rbp+4Fh+var_68], xmm0
0x1800262c7  movups  [rbp+4Fh+var_58], xmm0
0x1800262cb  movups  [rbp+4Fh+var_B0], xmm1
0x1800262cf  movups  [rbp+4Fh+var_A0], xmm1
0x1800262d3  movups  [rbp+4Fh+var_90], xmm1
0x1800262d7  cmp     edx, 0FFFFFFFFh
0x1800262da  jz      short loc_180026307
0x1800262dc  lea     rax, [r9+44h]
0x1800262e0  xor     r8d, r8d; wchar_t *
0x1800262e3  lea     rbx, [r9+40h]
0x1800262e7  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 *
0x1800262ec  add     r9, 38h ; '8'; wchar_t **
0x1800262f0  mov     [rsp+0E0h+var_C0], rbx; unsigned int *
0x1800262f5  mov     rcx, r10; lpSource
0x1800262f8  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x1800262fd  test    eax, eax
0x1800262ff  jnz     loc_1800263F2
0x180026305  add     edi, [rbx]
0x180026307  mov     rdx, [r15+18h]; struct TemplateResource *
0x18002630b  xor     esi, esi
0x18002630d  test    rdx, rdx
0x180026310  jz      short loc_180026336
0x180026312  lea     r8, [rbp+4Fh+var_78]; struct TemplateResourceData *
0x180026316  mov     rcx, r13; this
0x180026319  call    ?GetTemplateResource@PublisherManifestResource@@QEBAKPEBUTemplateResource@@AEAUTemplateResourceData@@@Z; PublisherManifestResource::GetTemplateResource(TemplateResource const *,TemplateResourceData &)
0x18002631e  test    eax, eax
0x180026320  jnz     loc_1800263F2
0x180026326  mov     esi, dword ptr [rbp+4Fh+var_68]
0x180026329  test    esi, esi
0x18002632b  jz      short loc_180026336
0x18002632d  lea     eax, [rsi+rsi*2]
0x180026330  lea     edi, [rdi+rax*8]
0x180026333  add     edi, 0FFFFFFE8h
0x180026336  mov     eax, esi
0x180026338  imul    rbx, rax, 58h ; 'X'
0x18002633c  call    cs:__imp_GetProcessHeap
0x180026342  mov     r8, rbx; dwBytes
0x180026345  mov     ebx, 8
0x18002634a  mov     edx, ebx; dwFlags
0x18002634c  mov     rcx, rax; hHeap
0x18002634f  call    cs:__imp_HeapAlloc
0x180026355  mov     [r14+30h], rax
0x180026359  test    rax, rax
0x18002635c  jnz     short loc_180026365
0x18002635e  mov     eax, ebx
0x180026360  jmp     loc_1800263F2
0x180026365  mov     r12, qword ptr [rbp+4Fh+var_68+8]
0x180026369  xor     ebx, ebx
0x18002636b  cmp     ebx, esi
0x18002636d  jnb     short loc_1800263EA
0x18002636f  lea     rax, [rbx+rbx*4]
0x180026373  mov     r15d, ebx
0x180026376  lea     r8, [r12+rax*4]; struct TypeResource *
0x18002637a  mov     rcx, r13; this
0x18002637d  lea     r9, [rbp+4Fh+var_B0]; struct TypeResourceData *
0x180026381  lea     rdx, [rbp+4Fh+var_78]; struct TemplateResourceData *
0x180026385  call    ?GetTypeResource@PublisherManifestResource@@QEBAKPEBUTemplateResourceData@@PEBUTypeResource@@AEAUTypeResourceData@@@Z; PublisherManifestResource::GetTypeResource(TemplateResourceData const *,TypeResource const *,TypeResourceData &)
0x18002638a  test    eax, eax
0x18002638c  jnz     short loc_1800263F2
0x18002638e  movups  xmm0, [rbp+4Fh+var_B0]
0x180026392  mov     r12, qword ptr [rbp+4Fh+var_68+8]
0x180026396  lea     r9, [rbp+4Fh+arg_8]
0x18002639a  movups  xmm1, [rbp+4Fh+var_A0]
0x18002639e  mov     [rbp+4Fh+arg_8], eax
0x1800263a1  mov     rcx, r13; this
0x1800263a4  lea     rax, [rbx+rbx*4]
0x1800263a8  imul    r8, r15, 58h ; 'X'
0x1800263ac  lea     rdx, [r12+rax*4]
0x1800263b0  add     r8, [r14+30h]
0x1800263b4  mov     [rsp+0E0h+var_C0], r8; __int64
0x1800263b9  movups  xmmword ptr [r8], xmm0
0x1800263bd  movups  xmm0, [rbp+4Fh+var_90]
0x1800263c1  movups  xmmword ptr [r8+10h], xmm1
0x1800263c6  movsd   xmm1, [rbp+4Fh+var_80]
0x1800263cb  movups  xmmword ptr [r8+20h], xmm0
0x1800263d0  movsd   qword ptr [r8+30h], xmm1
0x1800263d6  lea     r8, [rbp+4Fh+var_B0]
0x1800263da  call    GetEventPropertyInfoManifest
0x1800263df  test    eax, eax
0x1800263e1  jnz     short loc_1800263F2
0x1800263e3  add     edi, [rbp+4Fh+arg_8]
0x1800263e6  inc     ebx
0x1800263e8  jmp     short loc_18002636B
0x1800263ea  mov     rax, [rbp+4Fh+arg_20]
0x1800263ee  mov     [rax], edi
0x1800263f0  xor     eax, eax
0x1800263f2  add     rsp, 0A8h
0x1800263f9  pop     r15
0x1800263fb  pop     r14
0x1800263fd  pop     r13
0x1800263ff  pop     r12
0x180026401  pop     rdi
0x180026402  pop     rsi
0x180026403  pop     rbx
0x180026404  pop     rbp
0x180026405  retn
```
