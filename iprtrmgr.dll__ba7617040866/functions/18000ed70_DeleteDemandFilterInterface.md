# DeleteDemandFilterInterface

- ea: `0x18000ed70`
- end: `0x18000ef02`
- name: `DeleteDemandFilterInterface`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012190`
- `0x180016734`

## callees

- `0x18000ed70`
- `0x180011790`
- `0x180053d48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000ee2d`
- `KERNEL32!HeapFree` at `0x18000ee2d`

## string_xrefs

- `0x18000edf5`: `Entered: DeleteDemandFilterInterface`
- `0x18000ee56`: `DeleteDemandFilterInterface: No context, assuming interface %ws not added to filter driver`
- `0x18000ee4f`: `DeleteDemandFilterInterface: No context, assuming V6 interface %ws not added to filter driver`
- `0x18000eea9`: `Leaving: DeleteDemandFilterInterface`

## pseudocode

```c
__int64 __fastcall DeleteDemandFilterInterface(__int64 a1)
{
  InterfaceContainer *v2; // rcx
  void *v3; // r8
  void *v4; // rdx
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  const wchar_t *v7; // r8
  _OWORD v9[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+5Ch] [rbp-A4h]
  __int128 v12; // [rsp+6Ch] [rbp-94h]
  int v13; // [rsp+7Ch] [rbp-84h]
  int v14; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v15[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v9[0] = *(_OWORD *)(a1 + 688);
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  v9[1] = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v10) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: DeleteDemandFilterInterface",
      (unsigned int)v9,
      0,
      (__int64)&v10);
  }
  v3 = *(void **)(a1 + 128);
  if ( v3 )
  {
    HeapFree(IPRouterHeap, 0, v3);
    *(_QWORD *)(a1 + 128) = 0;
  }
  v4 = *(void **)(a1 + 104);
  if ( v4 == (void *)-1LL )
  {
    v5 = L"DeleteDemandFilterInterface: No context, assuming interface %ws not added to filter driver";
    if ( !*(_DWORD *)(a1 + 516) )
      v5 = L"DeleteDemandFilterInterface: No context, assuming V6 interface %ws not added to filter driver";
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = *(_QWORD *)(a1 + 72);
      LOWORD(v14) = 0;
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v14, v5, v6);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v7 = (const wchar_t *)&v14;
LABEL_13:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (_DWORD)v7,
          (unsigned int)v9,
          0,
          (__int64)&v10);
      }
    }
  }
  else
  {
    InterfaceContainer::DeleteInterface(v2, v4);
    *(_QWORD *)(a1 + 104) = -1;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = L"Leaving: DeleteDemandFilterInterface";
      LOWORD(v10) = 0;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp-8+arg_8], rbx
0x18000ed75  push    rbp
0x18000ed76  lea     rbp, [rsp-790h]
0x18000ed7e  sub     rsp, 890h
0x18000ed85  mov     rax, cs:__security_cookie
0x18000ed8c  xor     rax, rsp
0x18000ed8f  mov     [rbp+790h+var_10], rax
0x18000ed96  mov     rbx, rcx
0x18000ed99  xor     eax, eax
0x18000ed9b  lea     rcx, [rbp+790h+var_80C]; void *
0x18000ed9f  mov     [rbp+790h+var_810], eax
0x18000eda2  xor     edx, edx; Val
0x18000eda4  mov     r8d, 7FCh; Size
0x18000edaa  call    memset_0
0x18000edaf  movups  xmm1, xmmword ptr [rbx+2B0h]
0x18000edb6  xor     eax, eax
0x18000edb8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000edbf  xorps   xmm0, xmm0
0x18000edc2  movdqu  [rsp+890h+var_858], xmm1
0x18000edc8  mov     [rsp+890h+var_838], eax
0x18000edcc  movups  [rsp+890h+var_834], xmm0
0x18000edd1  mov     [rsp+890h+var_814], eax
0x18000edd5  movups  [rsp+890h+var_824], xmm0
0x18000edda  movups  [rsp+890h+var_848], xmm0
0x18000eddf  jz      short loc_18000EE18
0x18000ede1  mov     word ptr [rsp+890h+var_838], ax
0x18000ede6  lea     r9, [rsp+890h+var_858]
0x18000edeb  lea     rax, [rsp+890h+var_838]
0x18000edf0  mov     [rsp+890h+var_868], rax
0x18000edf5  lea     r8, aEnteredDeleted; "Entered: DeleteDemandFilterInterface"
0x18000edfc  lea     rdx, RasRtrmgrParamTraceInfo
0x18000ee03  mov     [rsp+890h+var_870], 0
0x18000ee0c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ee13  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ee18  mov     r8, [rbx+80h]; lpMem
0x18000ee1f  test    r8, r8
0x18000ee22  jz      short loc_18000EE3E
0x18000ee24  mov     rcx, cs:IPRouterHeap; hHeap
0x18000ee2b  xor     edx, edx; dwFlags
0x18000ee2d  call    cs:__imp_HeapFree
0x18000ee33  mov     qword ptr [rbx+80h], 0
0x18000ee3e  mov     rdx, [rbx+68h]; void *
0x18000ee42  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000ee46  jnz     short loc_18000EE91
0x18000ee48  cmp     dword ptr [rbx+204h], 0
0x18000ee4f  lea     rax, aDeletedemandfi_0; "DeleteDemandFilterInterface: No context"...
0x18000ee56  lea     rdx, aDeletedemandfi; "DeleteDemandFilterInterface: No context"...
0x18000ee5d  cmovz   rdx, rax
0x18000ee61  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000ee68  jge     short loc_18000EEE0
0x18000ee6a  mov     r8, [rbx+48h]
0x18000ee6e  lea     rcx, [rbp+790h+var_810]
0x18000ee72  xor     eax, eax
0x18000ee74  mov     word ptr [rbp+790h+var_810], ax
0x18000ee78  mov     word ptr [rsp+890h+var_838], ax
0x18000ee7d  call    FormatRRASErrorString
0x18000ee82  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000ee89  jge     short loc_18000EEE0
0x18000ee8b  lea     r8, [rbp+790h+var_810]
0x18000ee8f  jmp     short loc_18000EEB5
0x18000ee91  call    ?DeleteInterface@InterfaceContainer@@QEAAKPEAX@Z; InterfaceContainer::DeleteInterface(void *)
0x18000ee96  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x18000ee9e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000eea5  jz      short loc_18000EEE0
0x18000eea7  xor     eax, eax
0x18000eea9  lea     r8, aLeavingDeleted; "Leaving: DeleteDemandFilterInterface"
0x18000eeb0  mov     word ptr [rsp+890h+var_838], ax
0x18000eeb5  lea     rax, [rsp+890h+var_838]
0x18000eeba  mov     [rsp+890h+var_868], rax
0x18000eebf  lea     r9, [rsp+890h+var_858]
0x18000eec4  lea     rdx, RasRtrmgrParamTraceInfo
0x18000eecb  mov     [rsp+890h+var_870], 0
0x18000eed4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000eedb  call    McTemplateU0zjzz_EventWriteTransfer
0x18000eee0  xor     eax, eax
0x18000eee2  mov     rcx, [rbp+790h+var_10]
0x18000eee9  xor     rcx, rsp; StackCookie
0x18000eeec  call    __security_check_cookie
0x18000eef1  mov     rbx, [rsp+890h+arg_8]
0x18000eef9  add     rsp, 890h
0x18000ef00  pop     rbp
0x18000ef01  retn
```
