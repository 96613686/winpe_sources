# TFlatIsoMessage<LCIE_WEBDRIVER_INCREASE_TIMEOUT_PARAMS>::Post(ulong,ulong,ulong,ulong,LCIE_WEBDRIVER_INCREASE_TIMEOUT_PARAMS const *)

- ea: `0x180068064`
- end: `0x18006810d`
- name: `?Post@?$TFlatIsoMessage@ULCIE_WEBDRIVER_INCREASE_TIMEOUT_PARAMS@@@@SAJKKKKPEBULCIE_WEBDRIVER_INCREASE_TIMEOUT_PARAMS@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180067dd8`

## callees

- `0x180068064`

## import_xrefs

- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180068099`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180068099`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1800680f5`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1800680f5`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x1800680e5`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x1800680e5`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800680b7`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800680b7`

## pseudocode

```c
__int64 __fastcall TFlatIsoMessage<LCIE_WEBDRIVER_INCREASE_TIMEOUT_PARAMS>::Post(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  int v7; // ebx
  struct _IsoMessage *v9; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID v10; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  v9 = 0;
  v7 = IsoAllocMessageBuffer(a1, &v11, 0x24u, &v9);
  if ( v7 >= 0 )
  {
    *((_DWORD *)v9 + 8) = *a5;
    v10 = *(struct _GUID *)GlobalThreadState();
    v7 = IsoPostMessage(a1, a2, 0xD89u, 0, v11, &v10);
    if ( v7 < 0 )
      IsoFreeMessageBuffer(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180068064  mov     rax, rsp
0x180068067  mov     [rax+8], rbx
0x18006806b  mov     [rax+10h], rsi
0x18006806f  mov     [rax+20h], r9d
0x180068073  push    rdi
0x180068074  sub     rsp, 50h
0x180068078  mov     esi, edx
0x18006807a  mov     dword ptr [rax+20h], 0
0x180068081  lea     rdx, [rax+20h]
0x180068085  mov     qword ptr [rax-28h], 0
0x18006808d  lea     r9, [rax-28h]
0x180068091  mov     r8d, 24h ; '$'
0x180068097  mov     edi, ecx
0x180068099  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x18006809f  mov     ebx, eax
0x1800680a1  test    eax, eax
0x1800680a3  js      short loc_1800680FB
0x1800680a5  mov     rax, [rsp+58h+arg_20]
0x1800680ad  mov     ecx, [rax]
0x1800680af  mov     rax, [rsp+58h+var_28]
0x1800680b4  mov     [rax+20h], ecx
0x1800680b7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800680bd  mov     ecx, [rsp+58h+arg_18]
0x1800680c1  xor     r9d, r9d
0x1800680c4  mov     r8d, 0D89h
0x1800680ca  mov     edx, esi
0x1800680cc  movups  xmm0, xmmword ptr [rax]
0x1800680cf  lea     rax, [rsp+58h+var_18]
0x1800680d4  mov     [rsp+58h+var_30], rax
0x1800680d9  mov     [rsp+58h+var_38], ecx
0x1800680dd  mov     ecx, edi
0x1800680df  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x1800680e5  call    cs:__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z; IsoPostMessage(ulong,ulong,ulong,ulong,ulong,_GUID)
0x1800680eb  mov     ebx, eax
0x1800680ed  test    eax, eax
0x1800680ef  jns     short loc_1800680FB
0x1800680f1  mov     ecx, [rsp+58h+arg_18]
0x1800680f5  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x1800680fb  mov     rsi, [rsp+58h+arg_8]
0x180068100  mov     eax, ebx
0x180068102  mov     rbx, [rsp+58h+arg_0]
0x180068107  add     rsp, 50h
0x18006810b  pop     rdi
0x18006810c  retn
```
