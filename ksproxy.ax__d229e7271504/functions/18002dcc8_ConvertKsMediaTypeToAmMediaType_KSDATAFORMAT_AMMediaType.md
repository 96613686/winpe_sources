# ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)

- ea: `0x18002dcc8`
- end: `0x18002dd6a`
- name: `?ConvertKsMediaTypeToAmMediaType@@YAJPEATKSDATAFORMAT@@PEAU_AMMediaType@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(union KSDATAFORMAT *, struct _AMMediaType *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f8d0`
- `0x18002fa50`
- `0x1800315e0`

## callees

- `0x18002dcc8`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002dd22`
- `ole32!CoTaskMemAlloc` at `0x18002dd22`

## pseudocode

```c
__int64 __fastcall ConvertKsMediaTypeToAmMediaType(union KSDATAFORMAT *a1, struct _AMMediaType *a2)
{
  unsigned int v2; // esi
  unsigned int v5; // eax
  unsigned __int8 *v6; // rax

  v2 = 0;
  a2->majortype = (_GUID)*((_OWORD *)&a1->Alignment + 1);
  a2->subtype = (_GUID)*((_OWORD *)&a1->Alignment + 2);
  a2->formattype = (_GUID)*((_OWORD *)&a1->Alignment + 3);
  a2->bTemporalCompression = a1->Flags & 1;
  a2->lSampleSize = a1->SampleSize;
  a2->bFixedSizeSamples = a1->SampleSize != 0;
  if ( a1->FormatSize <= 0x40 )
  {
    a2->cbFormat = 0;
    a2->pbFormat = 0;
  }
  else
  {
    v5 = a1->FormatSize - 64;
    a2->cbFormat = v5;
    v6 = (unsigned __int8 *)CoTaskMemAlloc(v5);
    a2->pbFormat = v6;
    if ( v6 )
      memcpy_0(v6, &a1[1], a2->cbFormat);
    else
      return (unsigned int)-2147024882;
  }
  return v2;
}

```

## disassembly

```asm
0x18002dcc8  mov     [rsp+arg_0], rbx
0x18002dccd  mov     [rsp+arg_8], rsi
0x18002dcd2  push    rdi
0x18002dcd3  sub     rsp, 20h
0x18002dcd7  movups  xmm0, xmmword ptr [rcx+10h]
0x18002dcdb  xor     esi, esi
0x18002dcdd  mov     rbx, rdx
0x18002dce0  mov     rdi, rcx
0x18002dce3  movdqu  xmmword ptr [rdx], xmm0
0x18002dce7  movups  xmm1, xmmword ptr [rcx+20h]
0x18002dceb  movdqu  xmmword ptr [rdx+10h], xmm1
0x18002dcf0  movups  xmm0, xmmword ptr [rcx+30h]
0x18002dcf4  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18002dcf9  mov     eax, [rcx+4]
0x18002dcfc  and     eax, 1
0x18002dcff  mov     [rdx+24h], eax
0x18002dd02  mov     eax, [rcx+8]
0x18002dd05  mov     [rdx+28h], eax
0x18002dd08  xor     eax, eax
0x18002dd0a  cmp     [rcx+8], eax
0x18002dd0d  setnz   al
0x18002dd10  mov     [rdx+20h], eax
0x18002dd13  mov     eax, [rcx]
0x18002dd15  cmp     eax, 40h ; '@'
0x18002dd18  jbe     short loc_18002DD50
0x18002dd1a  add     eax, 0FFFFFFC0h
0x18002dd1d  mov     ecx, eax; cb
0x18002dd1f  mov     [rdx+48h], eax
0x18002dd22  call    cs:__imp_CoTaskMemAlloc
0x18002dd29  nop     dword ptr [rax+rax+00h]
0x18002dd2e  mov     [rbx+50h], rax
0x18002dd32  test    rax, rax
0x18002dd35  jnz     short loc_18002DD3E
0x18002dd37  mov     esi, 8007000Eh
0x18002dd3c  jmp     short loc_18002DD57
0x18002dd3e  mov     r8d, [rbx+48h]; Size
0x18002dd42  lea     rdx, [rdi+40h]; Src
0x18002dd46  mov     rcx, rax; void *
0x18002dd49  call    memcpy_0
0x18002dd4e  jmp     short loc_18002DD57
0x18002dd50  mov     [rdx+48h], esi
0x18002dd53  mov     [rdx+50h], rsi
0x18002dd57  mov     rbx, [rsp+28h+arg_0]
0x18002dd5c  mov     eax, esi
0x18002dd5e  mov     rsi, [rsp+28h+arg_8]
0x18002dd63  add     rsp, 20h
0x18002dd67  pop     rdi
0x18002dd68  retn
```
