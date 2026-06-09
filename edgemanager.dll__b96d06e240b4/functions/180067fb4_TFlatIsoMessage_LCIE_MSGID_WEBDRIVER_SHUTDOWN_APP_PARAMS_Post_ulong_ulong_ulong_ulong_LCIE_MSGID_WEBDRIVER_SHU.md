# TFlatIsoMessage<LCIE_MSGID_WEBDRIVER_SHUTDOWN_APP_PARAMS>::Post(ulong,ulong,ulong,ulong,LCIE_MSGID_WEBDRIVER_SHUTDOWN_APP_PARAMS const *)

- ea: `0x180067fb4`
- end: `0x18006805d`
- name: `?Post@?$TFlatIsoMessage@ULCIE_MSGID_WEBDRIVER_SHUTDOWN_APP_PARAMS@@@@SAJKKKKPEBULCIE_MSGID_WEBDRIVER_SHUTDOWN_APP_PARAMS@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180067950`

## callees

- `0x180067fb4`

## import_xrefs

- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180067fe9`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180067fe9`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180068045`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180068045`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180068035`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180068035`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180068007`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180068007`

## pseudocode

```c
__int64 __fastcall TFlatIsoMessage<LCIE_MSGID_WEBDRIVER_SHUTDOWN_APP_PARAMS>::Post(
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
    v7 = IsoPostMessage(a1, a2, 0xCF9u, 0, v11, &v10);
    if ( v7 < 0 )
      IsoFreeMessageBuffer(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067fb4  mov     rax, rsp
0x180067fb7  mov     [rax+8], rbx
0x180067fbb  mov     [rax+10h], rsi
0x180067fbf  mov     [rax+20h], r9d
0x180067fc3  push    rdi
0x180067fc4  sub     rsp, 50h
0x180067fc8  mov     esi, edx
0x180067fca  mov     dword ptr [rax+20h], 0
0x180067fd1  lea     rdx, [rax+20h]
0x180067fd5  mov     qword ptr [rax-28h], 0
0x180067fdd  lea     r9, [rax-28h]
0x180067fe1  mov     r8d, 24h ; '$'
0x180067fe7  mov     edi, ecx
0x180067fe9  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x180067fef  mov     ebx, eax
0x180067ff1  test    eax, eax
0x180067ff3  js      short loc_18006804B
0x180067ff5  mov     rax, [rsp+58h+arg_20]
0x180067ffd  mov     ecx, [rax]
0x180067fff  mov     rax, [rsp+58h+var_28]
0x180068004  mov     [rax+20h], ecx
0x180068007  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18006800d  mov     ecx, [rsp+58h+arg_18]
0x180068011  xor     r9d, r9d
0x180068014  mov     r8d, 0CF9h
0x18006801a  mov     edx, esi
0x18006801c  movups  xmm0, xmmword ptr [rax]
0x18006801f  lea     rax, [rsp+58h+var_18]
0x180068024  mov     [rsp+58h+var_30], rax
0x180068029  mov     [rsp+58h+var_38], ecx
0x18006802d  mov     ecx, edi
0x18006802f  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180068035  call    cs:__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z; IsoPostMessage(ulong,ulong,ulong,ulong,ulong,_GUID)
0x18006803b  mov     ebx, eax
0x18006803d  test    eax, eax
0x18006803f  jns     short loc_18006804B
0x180068041  mov     ecx, [rsp+58h+arg_18]
0x180068045  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18006804b  mov     rsi, [rsp+58h+arg_8]
0x180068050  mov     eax, ebx
0x180068052  mov     rbx, [rsp+58h+arg_0]
0x180068057  add     rsp, 50h
0x18006805b  pop     rdi
0x18006805c  retn
```
