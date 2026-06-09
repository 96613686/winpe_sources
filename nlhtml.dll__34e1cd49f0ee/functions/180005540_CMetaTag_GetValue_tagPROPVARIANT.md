# CMetaTag::GetValue(tagPROPVARIANT * *)

- ea: `0x180005540`
- end: `0x18000564c`
- name: `?GetValue@CMetaTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(CMetaTag *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005540`
- `0x180005a1c`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005585`

## pseudocode

```c
__int64 __fastcall CMetaTag::GetValue(CMetaTag *this, struct tagPROPVARIANT **a2)
{
  int v4; // ecx
  struct tagPROPVARIANT *v5; // rax
  struct tagPROPVARIANT *v6; // rsi
  void *v7; // rax
  unsigned int v8; // edx
  _WORD *v9; // r9
  size_t v10; // rbx
  __int64 result; // rax
  __int64 v12; // rcx

  v4 = *((_DWORD *)this + 62);
  if ( v4 )
  {
    if ( v4 == 1 )
      return 2147751682LL;
    else
      return 2147500037LL;
  }
  v5 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v5->vt = 31;
  v7 = CoTaskMemAlloc(2LL * (unsigned int)(*((_DWORD *)this + 66) + 1));
  v6->hVal.QuadPart = (LONGLONG)v7;
  if ( !v7 )
  {
    CoTaskMemFree(v6);
    return 2147942414LL;
  }
  v8 = *((_DWORD *)this + 66);
  v9 = (_WORD *)*((_QWORD *)this + 32);
  if ( v8 && *((_DWORD *)this + 132) )
  {
    v12 = v8 - 1;
    if ( v9[v12] != 39 )
      LODWORD(v12) = *((_DWORD *)this + 66);
    v8 = v12;
    if ( (_DWORD)v12 )
    {
      if ( *v9 == 39 )
      {
        v8 = v12 - 1;
        ++v9;
      }
    }
  }
  v10 = 2LL * v8;
  memcpy_0(v7, v9, v10);
  *(_WORD *)(v10 + v6->hVal.QuadPart) = 0;
  *a2 = v6;
  ((void (__fastcall *)(_QWORD, _QWORD))FixPrivateChars)((LARGE_INTEGER)v6->hVal.QuadPart, *((unsigned int *)this + 66));
  result = 0;
  *((_DWORD *)this + 62) = 1;
  return result;
}

```

## disassembly

```asm
0x180005540  push    rbx
0x180005542  push    rsi
0x180005543  push    rdi
0x180005544  push    r14
0x180005546  sub     rsp, 28h
0x18000554a  mov     rdi, rcx
0x18000554d  mov     r14, rdx
0x180005550  mov     ecx, [rcx+0F8h]
0x180005556  test    ecx, ecx
0x180005558  jnz     loc_1800055FE
0x18000555e  mov     ecx, 18h; cb
0x180005563  call    cs:__imp_CoTaskMemAlloc
0x180005569  mov     rsi, rax
0x18000556c  test    rax, rax
0x18000556f  jz      loc_1800055F7
0x180005575  mov     word ptr [rax], 1Fh
0x18000557a  mov     ecx, [rdi+108h]
0x180005580  inc     ecx
0x180005582  add     rcx, rcx; cb
0x180005585  call    cs:__imp_CoTaskMemAlloc
0x18000558b  mov     [rsi+8], rax
0x18000558f  mov     r10, rax
0x180005592  test    rax, rax
0x180005595  jz      short loc_180005611
0x180005597  mov     edx, [rdi+108h]
0x18000559d  mov     r9, [rdi+100h]
0x1800055a4  test    edx, edx
0x1800055a6  jz      short loc_1800055B1
0x1800055a8  cmp     dword ptr [rdi+210h], 0
0x1800055af  jnz     short loc_18000561C
0x1800055b1  mov     eax, edx
0x1800055b3  mov     rcx, r10; void *
0x1800055b6  mov     rdx, r9; Src
0x1800055b9  lea     rbx, [rax+rax]
0x1800055bd  mov     r8, rbx; Size
0x1800055c0  call    memcpy_0
0x1800055c5  mov     rcx, [rsi+8]
0x1800055c9  xor     eax, eax
0x1800055cb  mov     [rbx+rcx], ax
0x1800055cf  mov     [r14], rsi
0x1800055d2  mov     rcx, [rsi+8]
0x1800055d6  mov     edx, [rdi+108h]
0x1800055dc  call    FixPrivateChars
0x1800055e1  xor     eax, eax
0x1800055e3  mov     dword ptr [rdi+0F8h], 1
0x1800055ed  add     rsp, 28h
0x1800055f1  pop     r14
0x1800055f3  pop     rdi
0x1800055f4  pop     rsi
0x1800055f5  pop     rbx
0x1800055f6  retn
0x1800055f7  mov     eax, 8007000Eh
0x1800055fc  jmp     short loc_1800055ED
0x1800055fe  cmp     ecx, 1
0x180005601  jnz     short loc_18000560A
0x180005603  mov     eax, 80041702h
0x180005608  jmp     short loc_1800055ED
0x18000560a  mov     eax, 80004005h
0x18000560f  jmp     short loc_1800055ED
0x180005611  mov     rcx, rsi; pv
0x180005614  call    cs:__imp_CoTaskMemFree
0x18000561a  jmp     short loc_1800055F7
0x18000561c  lea     ecx, [rdx-1]
0x18000561f  mov     r8d, 27h ; '''
0x180005625  cmp     r8w, [r9+rcx*2]
0x18000562a  cmovnz  ecx, edx
0x18000562d  mov     edx, ecx
0x18000562f  test    ecx, ecx
0x180005631  jz      loc_1800055B1
0x180005637  cmp     [r9], r8w
0x18000563b  jnz     loc_1800055B1
0x180005641  dec     edx
0x180005643  add     r9, 2
0x180005647  jmp     loc_1800055B1
```
