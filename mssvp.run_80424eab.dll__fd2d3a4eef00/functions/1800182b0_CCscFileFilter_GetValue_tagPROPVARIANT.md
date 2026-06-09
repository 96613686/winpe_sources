# CCscFileFilter::GetValue(tagPROPVARIANT * *)

- ea: `0x1800182b0`
- end: `0x1800183db`
- name: `?GetValue@CCscFileFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(CCscFileFilter *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018490`

## callees

- `0x1800182b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001837f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001837f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018370`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018370`

## pseudocode

```c
__int64 __fastcall CCscFileFilter::GetValue(CCscFileFilter *this, LPVOID *a2)
{
  unsigned int v4; // edi
  struct tagPROPVARIANT *v5; // rax
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  LARGE_INTEGER v12; // rax
  const WCHAR *v13; // rcx

  if ( a2 )
  {
    v5 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
    *a2 = v5;
    if ( !v5 )
      return (unsigned int)-2147024882;
    *(_OWORD *)&v5->vt = 0;
    v5->bstrblobVal.pData = 0;
    v4 = 0;
    v6 = *((_DWORD *)this + 18);
    if ( !v6 )
    {
      *(_WORD *)*a2 = 19;
      *((_DWORD *)*a2 + 2) = *((_DWORD *)this + 19);
      return v4;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      *(_WORD *)*a2 = 64;
      v12 = *(LARGE_INTEGER *)((char *)this + 80);
      goto LABEL_14;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      *(_WORD *)*a2 = 64;
      v12 = *(LARGE_INTEGER *)((char *)this + 88);
      goto LABEL_14;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
          {
            v4 = -2147418113;
            goto LABEL_18;
          }
          *(_WORD *)*a2 = 64;
          v12 = *(LARGE_INTEGER *)((char *)this + 104);
LABEL_14:
          *((LARGE_INTEGER *)*a2 + 1) = v12;
          return v4;
        }
        v13 = L"true";
        *(_WORD *)*a2 = 31;
      }
      else
      {
        *(_WORD *)*a2 = 31;
        v13 = (const WCHAR *)*((_QWORD *)this + 15);
      }
      v4 = SHStrDupW(v13, (LPWSTR *)*a2 + 1);
      if ( (v4 & 0x80000000) == 0 )
        return v4;
LABEL_18:
      CoTaskMemFree(*a2);
      *a2 = 0;
      return v4;
    }
    *(_WORD *)*a2 = 64;
    v12 = *(LARGE_INTEGER *)((char *)this + 96);
    goto LABEL_14;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x1800182b0  mov     [rsp+arg_0], rbx
0x1800182b5  mov     [rsp+arg_8], rsi
0x1800182ba  push    rdi
0x1800182bb  sub     rsp, 20h
0x1800182bf  mov     rbx, rdx
0x1800182c2  mov     rsi, rcx
0x1800182c5  test    rdx, rdx
0x1800182c8  jnz     short loc_1800182D4
0x1800182ca  mov     edi, 80004003h
0x1800182cf  jmp     loc_1800183C9
0x1800182d4  mov     ecx, 18h; cb
0x1800182d9  call    cs:__imp_CoTaskMemAlloc
0x1800182df  mov     [rbx], rax
0x1800182e2  test    rax, rax
0x1800182e5  jnz     short loc_1800182F1
0x1800182e7  mov     edi, 8007000Eh
0x1800182ec  jmp     loc_1800183C9
0x1800182f1  xor     ecx, ecx
0x1800182f3  xorps   xmm0, xmm0
0x1800182f6  movups  xmmword ptr [rax], xmm0
0x1800182f9  mov     [rax+10h], rcx
0x1800182fd  xor     edi, edi
0x1800182ff  mov     ecx, [rsi+48h]
0x180018302  test    ecx, ecx
0x180018304  jz      loc_1800183B8
0x18001830a  sub     ecx, 1
0x18001830d  jz      loc_1800183AA
0x180018313  sub     ecx, 1
0x180018316  jz      loc_18001839C
0x18001831c  sub     ecx, 1
0x18001831f  jz      short loc_18001838E
0x180018321  sub     ecx, 1
0x180018324  jz      short loc_18001835D
0x180018326  sub     ecx, 1
0x180018329  jz      short loc_18001834C
0x18001832b  cmp     ecx, 1
0x18001832e  jz      short loc_180018337
0x180018330  mov     edi, 8000FFFFh
0x180018335  jmp     short loc_18001837C
0x180018337  mov     rax, [rbx]
0x18001833a  mov     word ptr [rax], 40h ; '@'
0x18001833f  mov     rax, [rsi+68h]
0x180018343  mov     rcx, [rbx]
0x180018346  mov     [rcx+8], rax
0x18001834a  jmp     short loc_1800183C9
0x18001834c  mov     rax, [rbx]
0x18001834f  lea     rcx, aTrue; "true"
0x180018356  mov     word ptr [rax], 1Fh
0x18001835b  jmp     short loc_180018369
0x18001835d  mov     rax, [rbx]
0x180018360  mov     word ptr [rax], 1Fh
0x180018365  mov     rcx, [rsi+78h]; psz
0x180018369  mov     rdx, [rbx]
0x18001836c  add     rdx, 8; ppwsz
0x180018370  call    cs:__imp_SHStrDupW
0x180018376  mov     edi, eax
0x180018378  test    eax, eax
0x18001837a  jns     short loc_1800183C9
0x18001837c  mov     rcx, [rbx]; pv
0x18001837f  call    cs:__imp_CoTaskMemFree
0x180018385  mov     qword ptr [rbx], 0
0x18001838c  jmp     short loc_1800183C9
0x18001838e  mov     rax, [rbx]
0x180018391  mov     word ptr [rax], 40h ; '@'
0x180018396  mov     rax, [rsi+60h]
0x18001839a  jmp     short loc_180018343
0x18001839c  mov     rax, [rbx]
0x18001839f  mov     word ptr [rax], 40h ; '@'
0x1800183a4  mov     rax, [rsi+58h]
0x1800183a8  jmp     short loc_180018343
0x1800183aa  mov     rax, [rbx]
0x1800183ad  mov     word ptr [rax], 40h ; '@'
0x1800183b2  mov     rax, [rsi+50h]
0x1800183b6  jmp     short loc_180018343
0x1800183b8  mov     rax, [rbx]
0x1800183bb  mov     word ptr [rax], 13h
0x1800183c0  mov     rcx, [rbx]
0x1800183c3  mov     eax, [rsi+4Ch]
0x1800183c6  mov     [rcx+8], eax
0x1800183c9  mov     rbx, [rsp+28h+arg_0]
0x1800183ce  mov     eax, edi
0x1800183d0  mov     rsi, [rsp+28h+arg_8]
0x1800183d5  add     rsp, 20h
0x1800183d9  pop     rdi
0x1800183da  retn
```
