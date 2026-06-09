# ConvertVideoInfoToVideoInfo2

- ea: `0x18001be68`
- end: `0x18001bf58`
- name: `ConvertVideoInfoToVideoInfo2`
- size: `240`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009d70`
- `0x18000ab04`
- `0x180015a10`
- `0x18001657c`

## callees

- `0x18001be68`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001bebf`
- `ole32!CoTaskMemAlloc` at `0x18001bebf`
- `ole32!CoTaskMemFree` at `0x18001bf36`
- `ole32!CoTaskMemFree` at `0x18001bf36`

## pseudocode

```c
__int64 __fastcall ConvertVideoInfoToVideoInfo2(__int64 a1)
{
  unsigned int v2; // eax
  SIZE_T v3; // rcx
  __int64 result; // rax
  char *v5; // rdi
  _OWORD *v6; // rax
  int v7; // eax
  void *v8; // rcx

  if ( *(_QWORD *)(a1 + 44) != *(_QWORD *)&FORMAT_VideoInfo.Data1 )
    return 2147942487LL;
  if ( *(_QWORD *)(a1 + 52) != *(_QWORD *)FORMAT_VideoInfo.Data4 )
    return 2147942487LL;
  if ( !*(_QWORD *)(a1 + 80) )
    return 2147942487LL;
  v2 = *(_DWORD *)(a1 + 72);
  if ( v2 < 0x58 )
    return 2147942487LL;
  v3 = v2 + 24;
  if ( (unsigned int)v3 < v2 )
    return 2147942934LL;
  v5 = (char *)CoTaskMemAlloc(v3);
  if ( !v5 )
    return 2147942414LL;
  v6 = *(_OWORD **)(a1 + 80);
  *(_OWORD *)v5 = *v6;
  *((_OWORD *)v5 + 1) = v6[1];
  *((_OWORD *)v5 + 2) = v6[2];
  *((_OWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 8) = 0;
  memcpy_0(v5 + 72, (const void *)(*(_QWORD *)(a1 + 80) + 48LL), (unsigned int)(*(_DWORD *)(a1 + 72) - 48));
  *((_DWORD *)v5 + 14) = *((_DWORD *)v5 + 19);
  v7 = -*((_DWORD *)v5 + 20);
  if ( *((int *)v5 + 20) > 0 )
    v7 = *((_DWORD *)v5 + 20);
  *((_DWORD *)v5 + 15) = v7;
  v8 = *(void **)(a1 + 80);
  *(GUID *)(a1 + 44) = FORMAT_VideoInfo2;
  CoTaskMemFree(v8);
  *(_DWORD *)(a1 + 72) += 24;
  result = 0;
  *(_QWORD *)(a1 + 80) = v5;
  return result;
}

```

## disassembly

```asm
0x18001be68  mov     [rsp+arg_0], rbx
0x18001be6d  push    rdi
0x18001be6e  sub     rsp, 20h
0x18001be72  mov     rax, [rcx+2Ch]
0x18001be76  mov     rbx, rcx
0x18001be79  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18001be80  jnz     loc_18001BF48
0x18001be86  mov     rax, [rcx+34h]
0x18001be8a  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18001be91  jnz     loc_18001BF48
0x18001be97  cmp     qword ptr [rcx+50h], 0
0x18001be9c  jz      loc_18001BF48
0x18001bea2  mov     eax, [rcx+48h]
0x18001bea5  cmp     eax, 58h ; 'X'
0x18001bea8  jb      loc_18001BF48
0x18001beae  lea     ecx, [rax+18h]; cb
0x18001beb1  cmp     ecx, eax
0x18001beb3  jnb     short loc_18001BEBF
0x18001beb5  mov     eax, 80070216h
0x18001beba  jmp     loc_18001BF4D
0x18001bebf  call    cs:__imp_CoTaskMemAlloc
0x18001bec5  mov     rdi, rax
0x18001bec8  test    rax, rax
0x18001becb  jnz     short loc_18001BED4
0x18001becd  mov     eax, 8007000Eh
0x18001bed2  jmp     short loc_18001BF4D
0x18001bed4  mov     rax, [rbx+50h]
0x18001bed8  lea     rcx, [rdi+48h]; void *
0x18001bedc  movups  xmm0, xmmword ptr [rax]
0x18001bedf  movups  xmmword ptr [rdi], xmm0
0x18001bee2  movups  xmm1, xmmword ptr [rax+10h]
0x18001bee6  movups  xmmword ptr [rdi+10h], xmm1
0x18001beea  movups  xmm0, xmmword ptr [rax+20h]
0x18001beee  xor     eax, eax
0x18001bef0  xorps   xmm1, xmm1
0x18001bef3  movups  xmmword ptr [rdi+20h], xmm0
0x18001bef7  movups  xmmword ptr [rdi+30h], xmm1
0x18001befb  mov     [rdi+40h], rax
0x18001beff  mov     r8d, [rbx+48h]
0x18001bf03  mov     rdx, [rbx+50h]
0x18001bf07  sub     r8d, 30h ; '0'; Size
0x18001bf0b  add     rdx, 30h ; '0'; Src
0x18001bf0f  call    memcpy_0
0x18001bf14  mov     eax, [rdi+4Ch]
0x18001bf17  mov     [rdi+38h], eax
0x18001bf1a  mov     eax, [rdi+50h]
0x18001bf1d  neg     eax
0x18001bf1f  cmovs   eax, [rdi+50h]
0x18001bf23  mov     [rdi+3Ch], eax
0x18001bf26  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x18001bf2d  mov     rcx, [rbx+50h]; pv
0x18001bf31  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x18001bf36  call    cs:__imp_CoTaskMemFree
0x18001bf3c  add     dword ptr [rbx+48h], 18h
0x18001bf40  xor     eax, eax
0x18001bf42  mov     [rbx+50h], rdi
0x18001bf46  jmp     short loc_18001BF4D
0x18001bf48  mov     eax, 80070057h
0x18001bf4d  mov     rbx, [rsp+28h+arg_0]
0x18001bf52  add     rsp, 20h
0x18001bf56  pop     rdi
0x18001bf57  retn
```
