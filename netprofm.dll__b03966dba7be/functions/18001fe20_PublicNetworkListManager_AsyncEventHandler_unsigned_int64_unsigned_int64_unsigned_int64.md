# PublicNetworkListManager::AsyncEventHandler(unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18001fe20`
- end: `0x18001fef7`
- name: `?AsyncEventHandler@PublicNetworkListManager@@CAJ_K00@Z`
- size: `215`
- prototype: `__int64 __fastcall(PublicNetworkListManager *this, __int64, struct CLIENT_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008590`
- `0x18001fe20`
- `0x180023228`
- `0x180023388`
- `0x1800234e4`
- `0x1800236a0`
- `0x18002382c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fedf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fedf`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::AsyncEventHandler(
        PublicNetworkListManager *this,
        __int64 a2,
        struct CLIENT_CALLBACK_DATA *a3)
{
  unsigned int v4; // edi
  unsigned int v6; // eax

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5));
  v6 = *((_DWORD *)a3 + 4) & 0xFFFFFF00;
  if ( v6 )
  {
    switch ( v6 )
    {
      case 0x100u:
        PublicNetworkListManager::ForwardNetworkEvent(this, v4, a3);
        break;
      case 0x200u:
        PublicNetworkListManager::ForwardNetworkConnectionEvent(this, v4, a3);
        break;
      case 0x400u:
        PublicNetworkListManager::ForwardNetworkConnectionCostEvent(this, v4, a3);
        break;
      case 0x800u:
        PublicNetworkListManager::ForwardNetworkCostManagerEvent(this, v4, a3);
        break;
    }
  }
  else
  {
    PublicNetworkListManager::ForwardNetworkListEvent(this, v4, a3);
  }
  CoTaskMemFree(a3);
  return 0;
}

```

## disassembly

```asm
0x18001fe20  mov     [rsp+arg_0], rbx
0x18001fe25  mov     [rsp+arg_8], rsi
0x18001fe2a  push    rdi
0x18001fe2b  sub     rsp, 30h
0x18001fe2f  mov     rbx, r8
0x18001fe32  mov     rdi, rdx
0x18001fe35  mov     rsi, rcx
0x18001fe38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe3f  lea     rax, WPP_GLOBAL_Control
0x18001fe46  cmp     rcx, rax
0x18001fe49  jz      short loc_18001FE6D
0x18001fe4b  test    byte ptr [rcx+1Ch], 8
0x18001fe4f  jz      short loc_18001FE6D
0x18001fe51  mov     eax, [r8+14h]
0x18001fe55  mov     r9d, edi
0x18001fe58  mov     rcx, [rcx+10h]
0x18001fe5c  mov     [rsp+38h+var_10], eax
0x18001fe60  mov     eax, [r8+10h]
0x18001fe64  mov     [rsp+38h+var_18], eax
0x18001fe68  call    WPP_SF_DDD
0x18001fe6d  mov     eax, [rbx+10h]
0x18001fe70  and     eax, 0FFFFFF00h
0x18001fe75  jnz     short loc_18001FE86
0x18001fe77  mov     edx, edi; unsigned int
0x18001fe79  mov     r8, rbx; struct CLIENT_CALLBACK_DATA *
0x18001fe7c  mov     rcx, rsi; this
0x18001fe7f  call    ?ForwardNetworkListEvent@PublicNetworkListManager@@AEBAJKPEAUCLIENT_CALLBACK_DATA@@@Z; PublicNetworkListManager::ForwardNetworkListEvent(ulong,CLIENT_CALLBACK_DATA *)
0x18001fe84  jmp     short loc_18001FEDC
0x18001fe86  cmp     eax, 100h
0x18001fe8b  jnz     short loc_18001FE9C
0x18001fe8d  mov     edx, edi; unsigned int
0x18001fe8f  mov     r8, rbx; struct CLIENT_CALLBACK_DATA *
0x18001fe92  mov     rcx, rsi; this
0x18001fe95  call    ?ForwardNetworkEvent@PublicNetworkListManager@@AEBAJKPEAUCLIENT_CALLBACK_DATA@@@Z; PublicNetworkListManager::ForwardNetworkEvent(ulong,CLIENT_CALLBACK_DATA *)
0x18001fe9a  jmp     short loc_18001FEDC
0x18001fe9c  cmp     eax, 200h
0x18001fea1  jnz     short loc_18001FEB2
0x18001fea3  mov     edx, edi; unsigned int
0x18001fea5  mov     r8, rbx; struct CLIENT_CALLBACK_DATA *
0x18001fea8  mov     rcx, rsi; this
0x18001feab  call    ?ForwardNetworkConnectionEvent@PublicNetworkListManager@@AEBAJKPEAUCLIENT_CALLBACK_DATA@@@Z; PublicNetworkListManager::ForwardNetworkConnectionEvent(ulong,CLIENT_CALLBACK_DATA *)
0x18001feb0  jmp     short loc_18001FEDC
0x18001feb2  cmp     eax, 400h
0x18001feb7  jnz     short loc_18001FEC8
0x18001feb9  mov     edx, edi; unsigned int
0x18001febb  mov     r8, rbx; struct CLIENT_CALLBACK_DATA *
0x18001febe  mov     rcx, rsi; this
0x18001fec1  call    ?ForwardNetworkConnectionCostEvent@PublicNetworkListManager@@AEBAJKPEAUCLIENT_CALLBACK_DATA@@@Z; PublicNetworkListManager::ForwardNetworkConnectionCostEvent(ulong,CLIENT_CALLBACK_DATA *)
0x18001fec6  jmp     short loc_18001FEDC
0x18001fec8  cmp     eax, 800h
0x18001fecd  jnz     short loc_18001FEDC
0x18001fecf  mov     edx, edi; unsigned int
0x18001fed1  mov     r8, rbx; struct CLIENT_CALLBACK_DATA *
0x18001fed4  mov     rcx, rsi; this
0x18001fed7  call    ?ForwardNetworkCostManagerEvent@PublicNetworkListManager@@AEAAJKPEAUCLIENT_CALLBACK_DATA@@@Z; PublicNetworkListManager::ForwardNetworkCostManagerEvent(ulong,CLIENT_CALLBACK_DATA *)
0x18001fedc  mov     rcx, rbx; pv
0x18001fedf  call    cs:__imp_CoTaskMemFree
0x18001fee5  mov     rbx, [rsp+38h+arg_0]
0x18001feea  xor     eax, eax
0x18001feec  mov     rsi, [rsp+38h+arg_8]
0x18001fef1  add     rsp, 30h
0x18001fef5  pop     rdi
0x18001fef6  retn
```
