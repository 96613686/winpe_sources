# GetSQMConnectivityState(SQMConnectivityState *)

- ea: `0x18002503c`
- end: `0x18002510f`
- name: `?GetSQMConnectivityState@@YAJPEAW4SQMConnectivityState@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(enum SQMConnectivityState *, enum _CONNECTIVITY_CAPABILITY *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800245a8`
- `0x180025e10`

## callees

- `0x180024a6c`
- `0x18002503c`
- `0x18002c5a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250ef`

## pseudocode

```c
__int64 __fastcall GetSQMConnectivityState(
        enum SQMConnectivityState *a1,
        enum _CONNECTIVITY_CAPABILITY *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  int ConnectivityCapability; // eax
  int AdapterSettings; // ebx
  void *v7; // rdx
  int v8; // ecx
  _QWORD *i; // rax
  _QWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = 0;
  ConnectivityCapability = GetConnectivityCapability((enum _CONNECTIVITY_CAPABILITY *)&v13, a2, a3, a4);
  AdapterSettings = ConnectivityCapability;
  if ( ConnectivityCapability )
  {
    if ( ConnectivityCapability > 0 )
      return (unsigned __int16)ConnectivityCapability | 0x80070000;
  }
  else if ( v13 )
  {
    if ( v13 == 1 )
    {
      *(_DWORD *)a1 = 2;
    }
    else if ( v13 == 2 )
    {
      *(_DWORD *)a1 = 3;
    }
  }
  else
  {
    *(_OWORD *)pv = 0;
    v11[0] = 0;
    v11[1] = 0;
    AdapterSettings = CAdapter::_GetAdapterSettings(pv, (const struct CAdapter::tagCAdapterMatchValue *)v11);
    v7 = pv[0];
    if ( AdapterSettings >= 0 )
    {
      v8 = 0;
      for ( i = pv[0]; i; i = (_QWORD *)i[1] )
      {
        if ( *((_DWORD *)i + 25) != 24 && *((_DWORD *)i + 25) != 131 && *((_DWORD *)i + 26) == 1 )
        {
          v8 = 1;
          break;
        }
      }
      *(_DWORD *)a1 = v8;
    }
    CoTaskMemFree(v7);
  }
  return (unsigned int)AdapterSettings;
}

```

## disassembly

```asm
0x18002503c  mov     [rsp+arg_0], rbx
0x180025041  push    rdi
0x180025042  sub     rsp, 40h
0x180025046  mov     rdi, rcx
0x180025049  mov     [rsp+48h+arg_8], 0
0x180025051  lea     rcx, [rsp+48h+arg_8]; enum _CONNECTIVITY_CAPABILITY *
0x180025056  call    ?GetConnectivityCapability@@YAKPEAW4_CONNECTIVITY_CAPABILITY@@0PEAK1@Z; GetConnectivityCapability(_CONNECTIVITY_CAPABILITY *,_CONNECTIVITY_CAPABILITY *,ulong *,ulong *)
0x18002505b  mov     ebx, eax
0x18002505d  test    eax, eax
0x18002505f  jnz     loc_1800250F7
0x180025065  mov     edx, [rsp+48h+arg_8]
0x180025069  test    edx, edx
0x18002506b  jz      short loc_18002508B
0x18002506d  sub     edx, 1
0x180025070  jz      short loc_180025083
0x180025072  cmp     edx, 1
0x180025075  jnz     loc_180025102
0x18002507b  mov     dword ptr [rdi], 3
0x180025081  jmp     short loc_180025102
0x180025083  mov     dword ptr [rdi], 2
0x180025089  jmp     short loc_180025102
0x18002508b  xorps   xmm0, xmm0
0x18002508e  movdqu  xmmword ptr [rsp+48h+pv], xmm0
0x180025094  mov     [rsp+48h+var_28], 0
0x18002509d  mov     [rsp+48h+var_20], 0
0x1800250a6  lea     rdx, [rsp+48h+var_28]; struct CAdapter::tagCAdapterMatchValue *
0x1800250ab  lea     rcx, [rsp+48h+pv]; this
0x1800250b0  call    ?_GetAdapterSettings@CAdapter@@IEAAJPEBUtagCAdapterMatchValue@1@@Z; CAdapter::_GetAdapterSettings(CAdapter::tagCAdapterMatchValue const *)
0x1800250b5  mov     ebx, eax
0x1800250b7  mov     rdx, [rsp+48h+pv]
0x1800250bc  test    eax, eax
0x1800250be  js      short loc_1800250EC
0x1800250c0  xor     ecx, ecx
0x1800250c2  mov     rax, rdx
0x1800250c5  test    rax, rax
0x1800250c8  jz      short loc_1800250EA
0x1800250ca  cmp     dword ptr [rax+64h], 18h
0x1800250ce  jz      short loc_1800250DF
0x1800250d0  cmp     dword ptr [rax+64h], 83h
0x1800250d7  jz      short loc_1800250DF
0x1800250d9  cmp     dword ptr [rax+68h], 1
0x1800250dd  jz      short loc_1800250E5
0x1800250df  mov     rax, [rax+8]
0x1800250e3  jmp     short loc_1800250C5
0x1800250e5  mov     ecx, 1
0x1800250ea  mov     [rdi], ecx
0x1800250ec  mov     rcx, rdx; pv
0x1800250ef  call    cs:__imp_CoTaskMemFree
0x1800250f5  jmp     short loc_180025102
0x1800250f7  jle     short loc_180025102
0x1800250f9  movzx   ebx, ax
0x1800250fc  or      ebx, 80070000h
0x180025102  mov     eax, ebx
0x180025104  mov     rbx, [rsp+48h+arg_0]
0x180025109  add     rsp, 40h
0x18002510d  pop     rdi
0x18002510e  retn
```
