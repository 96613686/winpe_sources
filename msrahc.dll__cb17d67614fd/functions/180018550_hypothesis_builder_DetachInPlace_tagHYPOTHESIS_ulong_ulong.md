# _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)

- ea: `0x180018550`
- end: `0x1800185f5`
- name: `?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z`
- size: `165`
- prototype: `__int64 __fastcall(WCHAR **this, struct tagHYPOTHESIS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018378`

## callees

- `0x180018550`
- `0x1800185fc`
- `0x18001a178`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018591`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _hypothesis_builder::DetachInPlace(
        WCHAR **this,
        struct tagHYPOTHESIS *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  _OWORD *v10; // rcx
  WCHAR *v11; // rax
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  _hypothesis_builder::DoDetach((_hypothesis_builder *)this, (struct tagHYPOTHESIS **)&pv);
  v10 = pv;
  if ( pv )
  {
    *(_OWORD *)&a2->pwszClassName = *(_OWORD *)pv;
    *(_OWORD *)&a2->celt = v10[1];
    CoTaskMemFree(v10);
  }
  else
  {
    if ( *((_DWORD *)this + 4) || this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs(0, v8, v9);
    a2->pwszClassName = *this;
    v11 = this[1];
    *this = 0;
    a2->pwszDescription = v11;
    this[1] = 0;
    a2->celt = 0;
    a2->rgAttributes = 0;
  }
  *a3 = 1;
  if ( a4 )
    *a4 = 32;
  return 0;
}

```

## disassembly

```asm
0x180018550  push    rbx
0x180018552  push    rsi
0x180018553  push    rdi
0x180018554  push    r14
0x180018556  sub     rsp, 28h
0x18001855a  mov     rdi, rdx
0x18001855d  mov     [rsp+48h+pv], 0
0x180018566  lea     rdx, [rsp+48h+pv]; struct tagHYPOTHESIS **
0x18001856b  mov     rsi, r9
0x18001856e  mov     r14, r8
0x180018571  mov     rbx, rcx
0x180018574  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x180018579  mov     rcx, [rsp+48h+pv]; pv
0x18001857e  test    rcx, rcx
0x180018581  jz      short loc_180018599
0x180018583  movups  xmm0, xmmword ptr [rcx]
0x180018586  movups  xmmword ptr [rdi], xmm0
0x180018589  movups  xmm1, xmmword ptr [rcx+10h]
0x18001858d  movups  xmmword ptr [rdi+10h], xmm1
0x180018591  call    cs:__imp_CoTaskMemFree
0x180018597  jmp     short loc_1800185D7
0x180018599  cmp     dword ptr [rbx+10h], 0
0x18001859d  jnz     short loc_1800185A6
0x18001859f  cmp     qword ptr [rbx+18h], 0
0x1800185a4  jz      short loc_1800185AB
0x1800185a6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800185ab  mov     rax, [rbx]
0x1800185ae  mov     [rdi], rax
0x1800185b1  mov     rax, [rbx+8]
0x1800185b5  mov     qword ptr [rbx], 0
0x1800185bc  mov     [rdi+8], rax
0x1800185c0  mov     qword ptr [rbx+8], 0
0x1800185c8  mov     dword ptr [rdi+10h], 0
0x1800185cf  mov     qword ptr [rdi+18h], 0
0x1800185d7  mov     dword ptr [r14], 1
0x1800185de  test    rsi, rsi
0x1800185e1  jz      short loc_1800185E9
0x1800185e3  mov     dword ptr [rsi], 20h ; ' '
0x1800185e9  xor     eax, eax
0x1800185eb  add     rsp, 28h
0x1800185ef  pop     r14
0x1800185f1  pop     rdi
0x1800185f2  pop     rsi
0x1800185f3  pop     rbx
0x1800185f4  retn
```
