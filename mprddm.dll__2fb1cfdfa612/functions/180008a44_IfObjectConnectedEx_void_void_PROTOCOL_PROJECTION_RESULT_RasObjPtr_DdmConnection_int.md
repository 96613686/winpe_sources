# IfObjectConnectedEx(void *,void *,_PROTOCOL_PROJECTION_RESULT *,RasObjPtr<DdmConnection>,int)

- ea: `0x180008a44`
- end: `0x180008bcb`
- name: `?IfObjectConnectedEx@@YAKPEAX0PEAU_PROTOCOL_PROJECTION_RESULT@@V?$RasObjPtr@VDdmConnection@@@@H@Z`
- size: `391`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ed5c`
- `0x180036aa0`
- `0x180041cb0`

## callees

- `0x180007b7c`
- `0x18000897c`
- `0x180008a44`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008b82`
- `KERNEL32!HeapFree` at `0x180008b82`
- `rasman!RasSendNotification` at `0x180008af7`
- `rasman!RasSendNotification` at `0x180008af7`

## string_xrefs

- `0x180008b0e`: `RasSendNotification(INCOMING_CONNECTED) rc=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IfObjectConnectedEx(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, int a5)
{
  __int64 v7; // rax
  _DWORD *v8; // rax
  void *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+40h] [rbp-C0h] BYREF
  int *v17; // [rsp+50h] [rbp-B0h]
  int v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v15[1] = a4;
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64, bool))(*(_QWORD *)g_pIDimInterfaceTable + 104LL))(
    g_pIDimInterfaceTable,
    a1,
    a2,
    a3,
    a5 != 0);
  if ( !dword_1800C8654 )
  {
    v20 = 0;
    memset_0(v21, 0, sizeof(v21));
    v7 = *a4;
    v15[0] = v7;
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = (_DWORD *)DDMGetRasEvent(a2, v15);
    v9 = v8;
    if ( v8 )
    {
      *v8 = 0x8000;
      v10 = RasSendNotification(v8);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasSendNotification(INCOMING_CONNECTED) rc=0x%x", v10);
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&v21[2 * v12 - 4] );
          v17 = &v20;
          v18 = 2 * v12 + 2;
          v19 = 0;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
            v11,
            2u,
            &v16);
        }
      }
      HeapFree(hHeap, 0, v9);
    }
  }
  v13 = *a4;
  if ( *a4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
  return 0;
}

```

## disassembly

```asm
0x180008a44  push    rbp
0x180008a46  push    rbx
0x180008a47  push    rsi
0x180008a48  push    rdi
0x180008a49  lea     rbp, [rsp-778h]
0x180008a51  sub     rsp, 878h
0x180008a58  mov     rax, cs:__security_cookie
0x180008a5f  xor     rax, rsp
0x180008a62  mov     [rbp+790h+var_30], rax
0x180008a69  mov     rdi, r9
0x180008a6c  mov     rbx, rdx
0x180008a6f  mov     rdx, rcx
0x180008a72  mov     [rsp+890h+var_858], r9
0x180008a77  mov     r10, cs:g_pIDimInterfaceTable
0x180008a7e  mov     rax, [r10]
0x180008a81  xor     esi, esi
0x180008a83  cmp     [rbp+790h+arg_20], esi
0x180008a89  setnz   cl
0x180008a8c  mov     byte ptr [rsp+890h+var_870], cl
0x180008a90  mov     r9, r8
0x180008a93  mov     r8, rbx
0x180008a96  mov     rcx, r10
0x180008a99  mov     rax, [rax+68h]
0x180008a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa2  cmp     cs:dword_1800C8654, esi
0x180008aa8  jnz     loc_180008B89
0x180008aae  mov     [rsp+890h+var_830], esi
0x180008ab2  xor     edx, edx; Val
0x180008ab4  mov     r8d, 7FCh; Size
0x180008aba  lea     rcx, [rsp+890h+var_82C]; void *
0x180008abf  call    memset_0
0x180008ac4  mov     rax, [rdi]
0x180008ac7  mov     [rsp+890h+var_860], rax
0x180008acc  test    rax, rax
0x180008acf  jz      short loc_180008AD5
0x180008ad1  lock inc dword ptr [rax+8]
0x180008ad5  lea     rdx, [rsp+890h+var_860]
0x180008ada  mov     rcx, rbx
0x180008add  call    ?DDMGetRasEvent@@YAPEAU_RASEVENT@@PEAXV?$RasObjPtr@VDdmConnection@@@@@Z; DDMGetRasEvent(void *,RasObjPtr<DdmConnection>)
0x180008ae2  mov     rbx, rax
0x180008ae5  test    rax, rax
0x180008ae8  jz      loc_180008B89
0x180008aee  mov     dword ptr [rax], 8000h
0x180008af4  mov     rcx, rax
0x180008af7  call    cs:__imp_RasSendNotification
0x180008afd  test    cs:byte_1800C8404, 10h
0x180008b04  jz      short loc_180008B76
0x180008b06  mov     word ptr [rsp+890h+var_830], si
0x180008b0b  mov     r8d, eax
0x180008b0e  lea     rdx, aRassendnotific; "RasSendNotification(INCOMING_CONNECTED)"...
0x180008b15  lea     rcx, [rsp+890h+var_830]
0x180008b1a  call    FormatRRASErrorString
0x180008b1f  test    cs:byte_1800C8404, 10h
0x180008b26  jz      short loc_180008B76
0x180008b28  lea     rcx, [rsp+890h+var_830]
0x180008b2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b31  inc     rax
0x180008b34  cmp     [rcx+rax*2], si
0x180008b38  jnz     short loc_180008B31
0x180008b3a  lea     eax, ds:2[rax*2]
0x180008b41  lea     rcx, [rsp+890h+var_830]
0x180008b46  mov     [rsp+890h+var_840], rcx
0x180008b4b  mov     [rsp+890h+var_838], eax
0x180008b4f  mov     [rsp+890h+var_834], esi
0x180008b53  lea     rax, [rsp+890h+var_850]
0x180008b58  mov     [rsp+890h+var_870], rax
0x180008b5d  mov     r9d, 2
0x180008b63  lea     rdx, RasDdmTraceInfo
0x180008b6a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008b71  call    McGenEventWrite_EventWriteTransfer
0x180008b76  mov     r8, rbx; lpMem
0x180008b79  xor     edx, edx; dwFlags
0x180008b7b  mov     rcx, cs:hHeap; hHeap
0x180008b82  call    cs:__imp_HeapFree
0x180008b88  nop
0x180008b89  mov     rcx, [rdi]
0x180008b8c  test    rcx, rcx
0x180008b8f  jz      short loc_180008BAE
0x180008b91  or      eax, 0FFFFFFFFh
0x180008b94  lock xadd [rcx+8], eax
0x180008b99  cmp     eax, 1
0x180008b9c  jnz     short loc_180008BAE
0x180008b9e  mov     rax, [rcx]
0x180008ba1  mov     edx, 1
0x180008ba6  mov     rax, [rax]
0x180008ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bae  xor     eax, eax
0x180008bb0  mov     rcx, [rbp+790h+var_30]
0x180008bb7  xor     rcx, rsp; StackCookie
0x180008bba  call    __security_check_cookie
0x180008bbf  add     rsp, 878h
0x180008bc6  pop     rdi
0x180008bc7  pop     rsi
0x180008bc8  pop     rbx
0x180008bc9  pop     rbp
0x180008bca  retn
```
