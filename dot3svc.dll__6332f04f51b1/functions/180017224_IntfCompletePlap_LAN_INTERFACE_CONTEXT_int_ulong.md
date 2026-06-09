# IntfCompletePlap(_LAN_INTERFACE_CONTEXT *,int,ulong)

- ea: `0x180017224`
- end: `0x180017335`
- name: `?IntfCompletePlap@@YAKPEAU_LAN_INTERFACE_CONTEXT@@HK@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _LAN_INTERFACE_CONTEXT *, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800178cc`
- `0x180017a68`
- `0x18001f290`
- `0x18001f4d0`

## callees

- `0x18000a9c0`
- `0x180017224`
- `0x18001bf24`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800172ac`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800172ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017282`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017282`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017299`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IntfCompletePlap(struct _LAN_INTERFACE_CONTEXT *a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // edi
  struct _RPC_ASYNC_STATE *v5; // rbp
  unsigned int v6; // eax
  unsigned int Reply; // [rsp+68h] [rbp+10h] BYREF

  Reply = a3;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 125, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, a3);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 128));
  v5 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a1 + 55);
  *((_QWORD *)a1 + 55) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 128));
  if ( v5 )
  {
    v6 = RpcAsyncCompleteCall(v5, &Reply);
    v4 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v6);
      }
      if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) != 0 )
        McTemplateU0qqqjz_EtwEventWriteTransfer(
          (_DWORD)a1 + 8,
          (unsigned int)CompletePLAPFailed,
          v4,
          2133,
          0,
          (__int64)a1 + 8,
          *((_QWORD *)a1 + 15));
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180017224  mov     rax, rsp
0x180017227  mov     [rax+8], rbx
0x18001722b  mov     [rax+18h], rbp
0x18001722f  mov     [rax+10h], edx
0x180017232  push    rsi
0x180017233  push    rdi
0x180017234  push    r15
0x180017236  sub     rsp, 40h
0x18001723a  mov     rsi, rcx
0x18001723d  mov     [rax+10h], r8d
0x180017241  xor     edi, edi
0x180017243  mov     rcx, cs:WPP_GLOBAL_Control
0x18001724a  lea     r15, WPP_GLOBAL_Control
0x180017251  cmp     rcx, r15
0x180017254  jz      short loc_180017278
0x180017256  cmp     byte ptr [rcx+19h], 4
0x18001725a  jb      short loc_180017278
0x18001725c  test    byte ptr [rcx+1Ch], 1
0x180017260  jz      short loc_180017278
0x180017262  mov     rcx, [rcx+10h]
0x180017266  lea     edx, [rdi+7Dh]
0x180017269  mov     r9d, r8d
0x18001726c  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180017273  call    WPP_SF_d
0x180017278  lea     rbx, [rsi+80h]
0x18001727f  mov     rcx, rbx; lpCriticalSection
0x180017282  call    cs:__imp_EnterCriticalSection
0x180017288  mov     rbp, [rsi+1B8h]
0x18001728f  mov     rcx, rbx; lpCriticalSection
0x180017292  mov     [rsi+1B8h], rdi
0x180017299  call    cs:__imp_LeaveCriticalSection
0x18001729f  test    rbp, rbp
0x1800172a2  jz      short loc_180017320
0x1800172a4  lea     rdx, [rsp+58h+Reply]; Reply
0x1800172a9  mov     rcx, rbp; pAsync
0x1800172ac  call    cs:__imp_RpcAsyncCompleteCall
0x1800172b2  mov     edi, eax
0x1800172b4  test    eax, eax
0x1800172b6  jz      short loc_180017320
0x1800172b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172bf  cmp     rcx, r15
0x1800172c2  jz      short loc_1800172E8
0x1800172c4  cmp     byte ptr [rcx+19h], 1
0x1800172c8  jb      short loc_1800172E8
0x1800172ca  test    byte ptr [rcx+1Ch], 1
0x1800172ce  jz      short loc_1800172E8
0x1800172d0  mov     rcx, [rcx+10h]
0x1800172d4  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800172db  mov     edx, 7Fh
0x1800172e0  mov     r9d, eax
0x1800172e3  call    WPP_SF_d
0x1800172e8  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x1800172ef  jz      short loc_180017320
0x1800172f1  mov     rax, [rsi+78h]
0x1800172f5  lea     rcx, [rsi+8]
0x1800172f9  mov     [rsp+58h+var_28], rax
0x1800172fe  lea     rdx, CompletePLAPFailed
0x180017305  mov     [rsp+58h+var_30], rcx
0x18001730a  mov     r9d, 855h
0x180017310  mov     r8d, edi
0x180017313  mov     [rsp+58h+var_38], 0
0x18001731b  call    McTemplateU0qqqjz_EtwEventWriteTransfer
0x180017320  mov     rbx, [rsp+58h+arg_0]
0x180017325  mov     eax, edi
0x180017327  mov     rbp, [rsp+58h+arg_10]
0x18001732c  add     rsp, 40h
0x180017330  pop     r15
0x180017332  pop     rdi
0x180017333  pop     rsi
0x180017334  retn
```
