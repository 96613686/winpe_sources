# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a170`
- end: `0x18000a21d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a230`

## callees

- `0x18000a170`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1456573935 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data2
        || a2[2] != *(_DWORD *)GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data4
        || a2[3] != *(_DWORD *)&GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
    }
    else
    {
      if ( *a2 != 1743621669
        || a2[1] != *(_DWORD *)&GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data2
        || a2[2] != *(_DWORD *)GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data4
        || a2[3] != *(_DWORD *)&GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
      a1 += 8;
    }
    *a3 = a1;
    goto LABEL_6;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    return (unsigned int)-2147467262;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x18000a170  push    rbx
0x18000a172  sub     rsp, 20h
0x18000a176  xor     ebx, ebx
0x18000a178  mov     [r8], rbx
0x18000a17b  cmp     [rdx], ebx
0x18000a17d  jnz     short loc_18000A1B1
0x18000a17f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000a185  cmp     [rdx+4], eax
0x18000a188  jnz     short loc_18000A1DA
0x18000a18a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000a190  cmp     [rdx+8], eax
0x18000a193  jnz     short loc_18000A1DA
0x18000a195  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000a19b  cmp     [rdx+0Ch], eax
0x18000a19e  jnz     short loc_18000A1DA
0x18000a1a0  mov     [r8], rcx
0x18000a1a3  mov     rax, [rcx]
0x18000a1a6  mov     rax, [rax+8]
0x18000a1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1af  jmp     short loc_18000A1DF
0x18000a1b1  cmp     dword ptr [rdx], 0A92E7211h
0x18000a1b7  jnz     short loc_18000A1E7
0x18000a1b9  mov     eax, dword ptr cs:_GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data2
0x18000a1bf  cmp     [rdx+4], eax
0x18000a1c2  jnz     short loc_18000A1DA
0x18000a1c4  mov     eax, dword ptr cs:_GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data4
0x18000a1ca  cmp     [rdx+8], eax
0x18000a1cd  jnz     short loc_18000A1DA
0x18000a1cf  mov     eax, dword ptr cs:_GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476.Data4+4
0x18000a1d5  cmp     [rdx+0Ch], eax
0x18000a1d8  jz      short loc_18000A214
0x18000a1da  mov     ebx, 80004002h
0x18000a1df  mov     eax, ebx
0x18000a1e1  add     rsp, 20h
0x18000a1e5  pop     rbx
0x18000a1e6  retn
0x18000a1e7  cmp     dword ptr [rdx], 67ED8E25h
0x18000a1ed  jnz     short loc_18000A1DA
0x18000a1ef  mov     eax, dword ptr cs:_GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data2
0x18000a1f5  cmp     [rdx+4], eax
0x18000a1f8  jnz     short loc_18000A1DA
0x18000a1fa  mov     eax, dword ptr cs:_GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data4
0x18000a200  cmp     [rdx+8], eax
0x18000a203  jnz     short loc_18000A1DA
0x18000a205  mov     eax, dword ptr cs:_GUID_67ed8e25_a748_4265_a6d4_8cdd80016333.Data4+4
0x18000a20b  cmp     [rdx+0Ch], eax
0x18000a20e  jnz     short loc_18000A1DA
0x18000a210  add     rcx, 8
0x18000a214  mov     rax, rcx
0x18000a217  mov     [r8], rcx
0x18000a21a  jmp     short loc_18000A1A3
```
