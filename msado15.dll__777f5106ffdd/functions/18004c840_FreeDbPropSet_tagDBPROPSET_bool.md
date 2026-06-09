# FreeDbPropSet(tagDBPROPSET *,bool)

- ea: `0x18004c840`
- end: `0x18004c8c9`
- name: `?FreeDbPropSet@@YAXPEAUtagDBPROPSET@@_N@Z`
- size: `137`
- prototype: `void __fastcall(struct tagDBPROPSET *, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18005c5f0`

## callees

- `0x18004c840`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18004c8bb`
- `MSDART!MpHeapFree` at `0x18004c8bb`
- `ole32!CoTaskMemFree` at `0x18004c897`
- `ole32!CoTaskMemFree` at `0x18004c897`
- `OLEAUT32!__imp_VariantClear` at `0x18004c874`
- `OLEAUT32!__imp_VariantClear` at `0x18004c874`

## pseudocode

```c
void __fastcall FreeDbPropSet(struct tagDBPROPSET *a1, char a2)
{
  __int64 v4; // rsi
  DBPROP *rgProperties; // rdx

  if ( a1->cProperties )
  {
    v4 = 0;
    do
    {
      VariantClear((VARIANTARG *)((char *)&a1->rgProperties->vValue + 64 * v4 + 8 * v4));
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < a1->cProperties );
    rgProperties = a1->rgProperties;
    if ( a2 )
    {
      CoTaskMemFree(a1->rgProperties);
    }
    else if ( rgProperties )
    {
      MpHeapFree(g_hHeapHandle, rgProperties);
    }
  }
}

```

## disassembly

```asm
0x18004c840  mov     [rsp+arg_8], rbx
0x18004c845  push    rdi
0x18004c846  sub     rsp, 20h
0x18004c84a  mov     eax, [rcx+8]
0x18004c84d  movzx   edi, dl
0x18004c850  mov     rbx, rcx
0x18004c853  test    eax, eax
0x18004c855  jz      short loc_18004C8A3
0x18004c857  mov     [rsp+28h+arg_0], rsi
0x18004c85c  xor     esi, esi
0x18004c85e  test    eax, eax
0x18004c860  jz      short loc_18004C887
0x18004c862  mov     rax, [rbx]
0x18004c865  lea     rcx, ds:6[rsi*8]
0x18004c86d  add     rcx, rsi
0x18004c870  lea     rcx, [rax+rcx*8]; pvarg
0x18004c874  call    cs:__imp_VariantClear
0x18004c87b  nop     dword ptr [rax+rax+00h]
0x18004c880  inc     esi
0x18004c882  cmp     esi, [rbx+8]
0x18004c885  jb      short loc_18004C862
0x18004c887  mov     rdx, [rbx]
0x18004c88a  mov     rsi, [rsp+28h+arg_0]
0x18004c88f  test    dil, dil
0x18004c892  jz      short loc_18004C8AF
0x18004c894  mov     rcx, rdx; pv
0x18004c897  call    cs:__imp_CoTaskMemFree
0x18004c89e  nop     dword ptr [rax+rax+00h]
0x18004c8a3  mov     rbx, [rsp+28h+arg_8]
0x18004c8a8  add     rsp, 20h
0x18004c8ac  pop     rdi
0x18004c8ad  retn
0x18004c8af  test    rdx, rdx
0x18004c8b2  jz      short loc_18004C8A3
0x18004c8b4  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004c8bb  call    cs:__imp_MpHeapFree
0x18004c8c2  nop     dword ptr [rax+rax+00h]
0x18004c8c7  jmp     short loc_18004C8A3
```
