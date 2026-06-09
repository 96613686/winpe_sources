# TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_SITE_MSG>::Post(ulong,ulong,ulong,ulong,LCIE_MSGID_F12_CREATE_DIAGNOSTICS_SITE_MSG const *)

- ea: `0x18006f150`
- end: `0x18006f213`
- name: `?Post@?$TFlatIsoMessage@ULCIE_MSGID_F12_CREATE_DIAGNOSTICS_SITE_MSG@@@@SAJKKKKPEBULCIE_MSGID_F12_CREATE_DIAGNOSTICS_SITE_MSG@@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006f21c`

## callees

- `0x18006f150`

## import_xrefs

- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18006f185`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18006f185`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18006f1fb`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18006f1fb`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x18006f1eb`
- `edgeIso!__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z` at `0x18006f1eb`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18006f1bd`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18006f1bd`

## pseudocode

```c
__int64 __fastcall TFlatIsoMessage<LCIE_MSGID_F12_CREATE_DIAGNOSTICS_SITE_MSG>::Post(
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
  v7 = IsoAllocMessageBuffer(a1, &v13, 0x5Cu, &v11);
  if ( v7 >= 0 )
  {
    v8 = a5;
    v9 = v11;
    *((_OWORD *)v11 + 2) = *a5;
    *((_OWORD *)v9 + 3) = v8[1];
    *((_OWORD *)v9 + 4) = v8[2];
    *(_OWORD *)((char *)v9 + 76) = *(_OWORD *)((char *)v8 + 44);
    v12 = *(struct _GUID *)GlobalThreadState();
    v7 = IsoPostMessage(a1, a2, 0xDDBu, 0, v13, &v12);
    if ( v7 < 0 )
      IsoFreeMessageBuffer(v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006f150  mov     rax, rsp
0x18006f153  mov     [rax+8], rbx
0x18006f157  mov     [rax+10h], rsi
0x18006f15b  mov     [rax+20h], r9d
0x18006f15f  push    rdi
0x18006f160  sub     rsp, 50h
0x18006f164  mov     esi, edx
0x18006f166  mov     dword ptr [rax+20h], 0
0x18006f16d  lea     rdx, [rax+20h]
0x18006f171  mov     qword ptr [rax-28h], 0
0x18006f179  lea     r9, [rax-28h]
0x18006f17d  mov     r8d, 5Ch ; '\'
0x18006f183  mov     edi, ecx
0x18006f185  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x18006f18b  mov     ebx, eax
0x18006f18d  test    eax, eax
0x18006f18f  js      short loc_18006F201
0x18006f191  mov     rax, [rsp+58h+arg_20]
0x18006f199  mov     rdx, [rsp+58h+var_28]
0x18006f19e  movups  xmm0, xmmword ptr [rax]
0x18006f1a1  movups  xmmword ptr [rdx+20h], xmm0
0x18006f1a5  movups  xmm1, xmmword ptr [rax+10h]
0x18006f1a9  movups  xmmword ptr [rdx+30h], xmm1
0x18006f1ad  movups  xmm0, xmmword ptr [rax+20h]
0x18006f1b1  movups  xmmword ptr [rdx+40h], xmm0
0x18006f1b5  movups  xmm1, xmmword ptr [rax+2Ch]
0x18006f1b9  movups  xmmword ptr [rdx+4Ch], xmm1
0x18006f1bd  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18006f1c3  mov     ecx, [rsp+58h+arg_18]
0x18006f1c7  xor     r9d, r9d
0x18006f1ca  mov     r8d, 0DDBh
0x18006f1d0  mov     edx, esi
0x18006f1d2  movups  xmm0, xmmword ptr [rax]
0x18006f1d5  lea     rax, [rsp+58h+var_18]
0x18006f1da  mov     [rsp+58h+var_30], rax
0x18006f1df  mov     [rsp+58h+var_38], ecx
0x18006f1e3  mov     ecx, edi
0x18006f1e5  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18006f1eb  call    cs:__imp_?IsoPostMessage@@YAJKKKKKU_GUID@@@Z; IsoPostMessage(ulong,ulong,ulong,ulong,ulong,_GUID)
0x18006f1f1  mov     ebx, eax
0x18006f1f3  test    eax, eax
0x18006f1f5  jns     short loc_18006F201
0x18006f1f7  mov     ecx, [rsp+58h+arg_18]
0x18006f1fb  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18006f201  mov     rsi, [rsp+58h+arg_8]
0x18006f206  mov     eax, ebx
0x18006f208  mov     rbx, [rsp+58h+arg_0]
0x18006f20d  add     rsp, 50h
0x18006f211  pop     rdi
0x18006f212  retn
```
