# CCscDirectoryFilter::GetValue(tagPROPVARIANT * *)

- ea: `0x180018490`
- end: `0x1800185ad`
- name: `?GetValue@CCscDirectoryFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CCscDirectoryFilter *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800182b0`
- `0x180018490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001859c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001859c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018511`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018511`

## pseudocode

```c
__int64 __fastcall CCscDirectoryFilter::GetValue(CCscDirectoryFilter *this, struct tagPROPVARIANT **a2)
{
  int v2; // eax
  unsigned int v5; // ebx
  struct tagPROPVARIANT *v6; // rax
  BYTE *v7; // rsi
  struct tagPROPVARIANT *v8; // rcx
  const WCHAR *v9; // rcx
  HRESULT v10; // eax
  LPWSTR ppwsz; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 120);
  if ( !v2 )
    return (unsigned int)CCscFileFilter::GetValue(this, a2);
  v5 = -2147215610;
  if ( v2 != 1 )
    return v5;
  v6 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  *a2 = v6;
  if ( v6 )
  {
    *(_OWORD *)&v6->vt = 0;
    v6->bstrblobVal.pData = 0;
    v7 = (BYTE *)CoTaskMemAlloc(0x30u);
    if ( v7 )
    {
      v9 = (const WCHAR *)*((_QWORD *)this + 38);
      ppwsz = 0;
      v10 = SHStrDupW(v9, &ppwsz);
      v8 = *a2;
      v5 = v10;
      if ( v10 >= 0 )
      {
        v8->vt = 4108;
        v5 = 268042;
        (*a2)->lVal = 2;
        (*a2)->bstrblobVal.pData = v7;
        *(*a2)->cai.pElems = 31;
        *((_QWORD *)(*a2)->bstrblobVal.pData + 1) = ppwsz;
        *((_WORD *)(*a2)->bstrblobVal.pData + 12) = 64;
        *((_QWORD *)(*a2)->bstrblobVal.pData + 4) = *(_QWORD *)((char *)this + 460);
        return v5;
      }
      goto LABEL_11;
    }
    v8 = *a2;
  }
  else
  {
    v8 = 0;
  }
  v7 = 0;
  v5 = -2147024882;
  ppwsz = 0;
LABEL_11:
  CoTaskMemFree(v8);
  *a2 = 0;
  if ( v7 )
    CoTaskMemFree(v7);
  return v5;
}

```

## disassembly

```asm
0x180018490  push    rbx
0x180018492  push    rbp
0x180018493  push    rsi
0x180018494  push    rdi
0x180018495  sub     rsp, 28h
0x180018499  mov     eax, [rcx+1E0h]
0x18001849f  mov     rdi, rdx
0x1800184a2  mov     rbp, rcx
0x1800184a5  test    eax, eax
0x1800184a7  jnz     short loc_1800184B5
0x1800184a9  call    ?GetValue@CCscFileFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z; CCscFileFilter::GetValue(tagPROPVARIANT * *)
0x1800184ae  mov     ebx, eax
0x1800184b0  jmp     loc_1800185A2
0x1800184b5  mov     ebx, 80041706h
0x1800184ba  cmp     eax, 1
0x1800184bd  jnz     loc_1800185A2
0x1800184c3  lea     ecx, [rax+17h]; cb
0x1800184c6  call    cs:__imp_CoTaskMemAlloc
0x1800184cc  mov     [rdi], rax
0x1800184cf  test    rax, rax
0x1800184d2  jz      loc_180018578
0x1800184d8  xor     ecx, ecx
0x1800184da  xorps   xmm0, xmm0
0x1800184dd  movups  xmmword ptr [rax], xmm0
0x1800184e0  mov     [rax+10h], rcx
0x1800184e4  mov     ecx, 30h ; '0'; cb
0x1800184e9  call    cs:__imp_CoTaskMemAlloc
0x1800184ef  mov     rsi, rax
0x1800184f2  test    rax, rax
0x1800184f5  jnz     short loc_1800184FC
0x1800184f7  mov     rcx, [rdi]
0x1800184fa  jmp     short loc_18001857B
0x1800184fc  mov     rcx, [rbp+130h]; psz
0x180018503  lea     rdx, [rsp+48h+ppwsz]; ppwsz
0x180018508  mov     [rsp+48h+ppwsz], 0
0x180018511  call    cs:__imp_SHStrDupW
0x180018517  mov     rcx, [rdi]
0x18001851a  mov     ebx, eax
0x18001851c  test    eax, eax
0x18001851e  js      short loc_180018587
0x180018520  mov     word ptr [rcx], 100Ch
0x180018525  mov     ebx, 4170Ah
0x18001852a  mov     rax, [rdi]
0x18001852d  mov     dword ptr [rax+8], 2
0x180018534  mov     rax, [rdi]
0x180018537  mov     [rax+10h], rsi
0x18001853b  mov     rax, [rdi]
0x18001853e  mov     rcx, [rax+10h]
0x180018542  mov     word ptr [rcx], 1Fh
0x180018547  mov     rax, [rdi]
0x18001854a  mov     rcx, [rax+10h]
0x18001854e  mov     rax, [rsp+48h+ppwsz]
0x180018553  mov     [rcx+8], rax
0x180018557  mov     rax, [rdi]
0x18001855a  mov     rcx, [rax+10h]
0x18001855e  mov     word ptr [rcx+18h], 40h ; '@'
0x180018564  mov     rax, [rdi]
0x180018567  mov     rcx, [rax+10h]
0x18001856b  mov     rax, [rbp+1CCh]
0x180018572  mov     [rcx+20h], rax
0x180018576  jmp     short loc_1800185A2
0x180018578  mov     rcx, rax; pv
0x18001857b  xor     esi, esi
0x18001857d  mov     ebx, 8007000Eh
0x180018582  mov     [rsp+48h+ppwsz], rsi
0x180018587  call    cs:__imp_CoTaskMemFree
0x18001858d  mov     qword ptr [rdi], 0
0x180018594  test    rsi, rsi
0x180018597  jz      short loc_1800185A2
0x180018599  mov     rcx, rsi; pv
0x18001859c  call    cs:__imp_CoTaskMemFree
0x1800185a2  mov     eax, ebx
0x1800185a4  add     rsp, 28h
0x1800185a8  pop     rdi
0x1800185a9  pop     rsi
0x1800185aa  pop     rbp
0x1800185ab  pop     rbx
0x1800185ac  retn
```
