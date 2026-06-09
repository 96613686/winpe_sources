# InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)

- ea: `0x180038758`
- end: `0x1800387fd`
- name: `?InitializeKsDataFormat@@YAJPEBU_AMMediaType@@PEAPEAXPEAK@Z`
- size: `165`
- prototype: `__int64 __fastcall(const struct _AMMediaType *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002da70`
- `0x180031360`

## callees

- `0x180038758`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180038778`
- `ole32!CoTaskMemAlloc` at `0x180038778`

## pseudocode

```c
__int64 __fastcall InitializeKsDataFormat(const struct _AMMediaType *a1, void **a2, unsigned int *a3)
{
  unsigned int v4; // eax
  _DWORD *v6; // rax

  v4 = a1->cbFormat + 64;
  if ( a1->cbFormat >= 0xFFFFFFC0 )
  {
    *a3 = -1;
    return 2147942934LL;
  }
  else
  {
    *a3 = v4;
    v6 = CoTaskMemAlloc(v4);
    *a2 = v6;
    if ( v6 )
    {
      *v6 = a1->cbFormat + 64;
      v6[1] = a1->bTemporalCompression != 0;
      *((_QWORD *)v6 + 1) = a1->lSampleSize;
      *((_OWORD *)v6 + 1) = a1->majortype;
      *((_OWORD *)v6 + 2) = a1->subtype;
      *((_OWORD *)v6 + 3) = a1->formattype;
      memcpy_0(v6 + 16, a1->pbFormat, a1->cbFormat);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180038758  mov     [rsp+arg_0], rbx
0x18003875d  push    rdi
0x18003875e  sub     rsp, 20h
0x180038762  mov     eax, [rcx+48h]
0x180038765  mov     rdi, rdx
0x180038768  add     eax, 40h ; '@'
0x18003876b  mov     rbx, rcx
0x18003876e  cmp     eax, 40h ; '@'
0x180038771  jb      short loc_1800387E5
0x180038773  mov     ecx, eax; cb
0x180038775  mov     [r8], eax
0x180038778  call    cs:__imp_CoTaskMemAlloc
0x18003877f  nop     dword ptr [rax+rax+00h]
0x180038784  mov     [rdi], rax
0x180038787  mov     rcx, rax
0x18003878a  test    rax, rax
0x18003878d  jnz     short loc_180038796
0x18003878f  mov     eax, 8007000Eh
0x180038794  jmp     short loc_1800387F1
0x180038796  mov     eax, [rbx+48h]
0x180038799  add     eax, 40h ; '@'
0x18003879c  mov     [rcx], eax
0x18003879e  xor     eax, eax
0x1800387a0  cmp     [rbx+24h], eax
0x1800387a3  setnz   al
0x1800387a6  mov     [rcx+4], eax
0x1800387a9  mov     eax, [rbx+28h]
0x1800387ac  mov     [rcx+8], eax
0x1800387af  mov     dword ptr [rcx+0Ch], 0
0x1800387b6  movups  xmm0, xmmword ptr [rbx]
0x1800387b9  movdqu  xmmword ptr [rcx+10h], xmm0
0x1800387be  movups  xmm1, xmmword ptr [rbx+10h]
0x1800387c2  movdqu  xmmword ptr [rcx+20h], xmm1
0x1800387c7  movups  xmm0, xmmword ptr [rbx+2Ch]
0x1800387cb  movdqu  xmmword ptr [rcx+30h], xmm0
0x1800387d0  mov     r8d, [rbx+48h]; Size
0x1800387d4  add     rcx, 40h ; '@'; void *
0x1800387d8  mov     rdx, [rbx+50h]; Src
0x1800387dc  call    memcpy_0
0x1800387e1  xor     eax, eax
0x1800387e3  jmp     short loc_1800387F1
0x1800387e5  mov     dword ptr [r8], 0FFFFFFFFh
0x1800387ec  mov     eax, 80070216h
0x1800387f1  mov     rbx, [rsp+28h+arg_0]
0x1800387f6  add     rsp, 20h
0x1800387fa  pop     rdi
0x1800387fb  retn
```
