# TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG const *)

- ea: `0x180072fa8`
- end: `0x18007305b`
- name: `?Post@?$TFlatIsoMessage@ULCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG@@@@SAJKKKKPEBULCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180072ccc`

## callees

- `0x18002c598`
- `0x180072fa8`

## import_xrefs

- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180072fdd`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180072fdd`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180073043`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180073043`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180073033`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180073033`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180073005`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180073005`

## pseudocode

```c
__int64 __fastcall TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_GET_TARGETS_REQUEST_MSG>::Post(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        void *Src)
{
  int v7; // ebx
  struct _IsoMessage *v9; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID v10; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  v9 = 0;
  v7 = IsoAllocMessageBuffer(a1, &v11, 0x1068u, &v9);
  if ( v7 >= 0 )
  {
    memcpy_0((char *)v9 + 32, Src, 0x1048u);
    v10 = *(struct _GUID *)GlobalThreadState();
    v7 = IsoPostMessage(a1, a2, 0xDEAu, 0, v11, &v10);
    if ( v7 < 0 )
      IsoFreeMessageBuffer(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180072fa8  mov     rax, rsp
0x180072fab  mov     [rax+8], rbx
0x180072faf  mov     [rax+10h], rsi
0x180072fb3  mov     [rax+20h], r9d
0x180072fb7  push    rdi
0x180072fb8  sub     rsp, 50h
0x180072fbc  mov     esi, edx
0x180072fbe  mov     dword ptr [rax+20h], 0
0x180072fc5  lea     rdx, [rax+20h]
0x180072fc9  mov     qword ptr [rax-28h], 0
0x180072fd1  lea     r9, [rax-28h]
0x180072fd5  mov     r8d, 1068h
0x180072fdb  mov     edi, ecx
0x180072fdd  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x180072fe3  mov     ebx, eax
0x180072fe5  test    eax, eax
0x180072fe7  js      short loc_180073049
0x180072fe9  mov     rcx, [rsp+58h+var_28]
0x180072fee  mov     r8d, 1048h; Size
0x180072ff4  mov     rdx, [rsp+58h+Src]; Src
0x180072ffc  add     rcx, 20h ; ' '; void *
0x180073000  call    memcpy_0
0x180073005  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18007300b  mov     ecx, [rsp+58h+arg_18]
0x18007300f  xor     r9d, r9d
0x180073012  mov     r8d, 0DEAh
0x180073018  mov     edx, esi
0x18007301a  movups  xmm0, xmmword ptr [rax]
0x18007301d  lea     rax, [rsp+58h+var_18]
0x180073022  mov     [rsp+58h+var_30], rax
0x180073027  mov     [rsp+58h+var_38], ecx
0x18007302b  mov     ecx, edi
0x18007302d  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180073033  call    cs:__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z; IsoPostMessage(ulong,ulong,ulong,ulong,ulong,_GUID)
0x180073039  mov     ebx, eax
0x18007303b  test    eax, eax
0x18007303d  jns     short loc_180073049
0x18007303f  mov     ecx, [rsp+58h+arg_18]
0x180073043  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x180073049  mov     rsi, [rsp+58h+arg_8]
0x18007304e  mov     eax, ebx
0x180073050  mov     rbx, [rsp+58h+arg_0]
0x180073055  add     rsp, 50h
0x180073059  pop     rdi
0x18007305a  retn
```
