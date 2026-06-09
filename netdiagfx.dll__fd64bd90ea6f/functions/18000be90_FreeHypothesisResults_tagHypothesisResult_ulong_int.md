# FreeHypothesisResults(tagHypothesisResult *,ulong,int)

- ea: `0x18000be90`
- end: `0x18000bed9`
- name: `?FreeHypothesisResults@@YAXPEAUtagHypothesisResult@@KH@Z`
- size: `73`
- prototype: `void __fastcall(struct tagHypothesisResult *pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008cf0`

## callees

- `0x18000be90`
- `0x18002b550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000beca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000beca`

## pseudocode

```c
void __fastcall FreeHypothesisResults(struct tagHypothesisResult *pv, unsigned int a2, int a3)
{
  __int64 v6; // rdi

  if ( pv && a2 )
  {
    v6 = 0;
    do
    {
      FreeHypothesesEmbeddedMemory(1u, &pv[v6].hypothesis);
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18000be90  test    rcx, rcx
0x18000be93  jz      short locret_18000BED8
0x18000be95  push    rbx
0x18000be96  push    rbp
0x18000be97  push    rsi
0x18000be98  push    rdi
0x18000be99  sub     rsp, 28h
0x18000be9d  mov     ebp, r8d
0x18000bea0  mov     esi, edx
0x18000bea2  mov     rbx, rcx
0x18000bea5  test    edx, edx
0x18000bea7  jz      short loc_18000BED0
0x18000bea9  xor     edi, edi
0x18000beab  lea     rcx, [rdi+rdi*4]
0x18000beaf  lea     rdx, [rbx+rcx*8]; struct tagHYPOTHESIS *
0x18000beb3  mov     ecx, 1; unsigned int
0x18000beb8  call    ?FreeHypothesesEmbeddedMemory@@YAXKPEAUtagHYPOTHESIS@@@Z; FreeHypothesesEmbeddedMemory(ulong,tagHYPOTHESIS *)
0x18000bebd  inc     edi
0x18000bebf  cmp     edi, esi
0x18000bec1  jb      short loc_18000BEAB
0x18000bec3  test    ebp, ebp
0x18000bec5  jz      short loc_18000BED0
0x18000bec7  mov     rcx, rbx; pv
0x18000beca  call    cs:__imp_CoTaskMemFree
0x18000bed0  add     rsp, 28h
0x18000bed4  pop     rdi
0x18000bed5  pop     rsi
0x18000bed6  pop     rbp
0x18000bed7  pop     rbx
0x18000bed8  retn
```
