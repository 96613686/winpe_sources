# TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_CLOSE_TAB_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_MSGID_DEVTOOLS_CLOSE_TAB_MSG const *)

- ea: `0x180072ed4`
- end: `0x180072f9f`
- name: `?Post@?$TFlatIsoMessage@ULCIE_MSGID_DEVTOOLS_CLOSE_TAB_MSG@@@@SAJKKKKPEBULCIE_MSGID_DEVTOOLS_CLOSE_TAB_MSG@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, __int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180072b00`

## callees

- `0x180072ed4`

## import_xrefs

- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180072f09`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180072f09`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180072f87`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180072f87`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180072f77`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x180072f77`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072f49`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180072f49`

## pseudocode

```c
__int64 __fastcall TFlatIsoMessage<LCIE_MSGID_DEVTOOLS_CLOSE_TAB_MSG>::Post(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  int v7; // ebx
  _OWORD *v8; // rax
  struct _IsoMessage *v9; // rdx
  struct _IsoMessage *v11; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID v12; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v11 = 0;
  v7 = IsoAllocMessageBuffer(a1, &v13, 0x70u, &v11);
  if ( v7 >= 0 )
  {
    v8 = a5;
    v9 = v11;
    *((_OWORD *)v11 + 2) = *a5;
    *((_OWORD *)v9 + 3) = v8[1];
    *((_OWORD *)v9 + 4) = v8[2];
    *((_OWORD *)v9 + 5) = v8[3];
    *((_OWORD *)v9 + 6) = v8[4];
    v12 = *(struct _GUID *)GlobalThreadState();
    v7 = IsoPostMessage(a1, a2, 0xD5Bu, 0, v13, &v12);
    if ( v7 < 0 )
      IsoFreeMessageBuffer(v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180072ed4  mov     rax, rsp
0x180072ed7  mov     [rax+8], rbx
0x180072edb  mov     [rax+10h], rsi
0x180072edf  mov     [rax+20h], r9d
0x180072ee3  push    rdi
0x180072ee4  sub     rsp, 50h
0x180072ee8  mov     esi, edx
0x180072eea  mov     dword ptr [rax+20h], 0
0x180072ef1  lea     rdx, [rax+20h]
0x180072ef5  mov     qword ptr [rax-28h], 0
0x180072efd  lea     r9, [rax-28h]
0x180072f01  mov     r8d, 70h ; 'p'
0x180072f07  mov     edi, ecx
0x180072f09  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x180072f0f  mov     ebx, eax
0x180072f11  test    eax, eax
0x180072f13  js      short loc_180072F8D
0x180072f15  mov     rax, [rsp+58h+arg_20]
0x180072f1d  mov     rdx, [rsp+58h+var_28]
0x180072f22  movaps  xmm0, xmmword ptr [rax]
0x180072f25  movups  xmmword ptr [rdx+20h], xmm0
0x180072f29  movaps  xmm1, xmmword ptr [rax+10h]
0x180072f2d  movups  xmmword ptr [rdx+30h], xmm1
0x180072f31  movaps  xmm0, xmmword ptr [rax+20h]
0x180072f35  movups  xmmword ptr [rdx+40h], xmm0
0x180072f39  movaps  xmm1, xmmword ptr [rax+30h]
0x180072f3d  movups  xmmword ptr [rdx+50h], xmm1
0x180072f41  movaps  xmm0, xmmword ptr [rax+40h]
0x180072f45  movups  xmmword ptr [rdx+60h], xmm0
0x180072f49  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180072f4f  mov     ecx, [rsp+58h+arg_18]
0x180072f53  xor     r9d, r9d
0x180072f56  mov     r8d, 0D5Bh
0x180072f5c  mov     edx, esi
0x180072f5e  movups  xmm0, xmmword ptr [rax]
0x180072f61  lea     rax, [rsp+58h+var_18]
0x180072f66  mov     [rsp+58h+var_30], rax
0x180072f6b  mov     [rsp+58h+var_38], ecx
0x180072f6f  mov     ecx, edi
0x180072f71  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180072f77  call    cs:__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z; IsoPostMessage(ulong,ulong,ulong,ulong,ulong,_GUID)
0x180072f7d  mov     ebx, eax
0x180072f7f  test    eax, eax
0x180072f81  jns     short loc_180072F8D
0x180072f83  mov     ecx, [rsp+58h+arg_18]
0x180072f87  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x180072f8d  mov     rsi, [rsp+58h+arg_8]
0x180072f92  mov     eax, ebx
0x180072f94  mov     rbx, [rsp+58h+arg_0]
0x180072f99  add     rsp, 50h
0x180072f9d  pop     rdi
0x180072f9e  retn
```
