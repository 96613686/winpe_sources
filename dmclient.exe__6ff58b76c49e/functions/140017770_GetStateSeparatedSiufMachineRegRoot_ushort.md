# GetStateSeparatedSiufMachineRegRoot(ushort * *)

- ea: `0x140017770`
- end: `0x140017853`
- name: `?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004fe0`
- `0x1400052f0`
- `0x140005830`
- `0x1400076e4`
- `0x14001785c`

## callees

- `0x140001d68`
- `0x140017770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400177b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400177b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400177a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017802`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400177a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017802`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017810`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1400177e9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1400177e9`

## string_xrefs

- `0x1400177e2`: `siufregistrystateroot`

## pseudocode

```c
__int64 __fastcall GetStateSeparatedSiufMachineRegRoot(unsigned __int16 **a1)
{
  signed int v2; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // rdi
  int PersistedRegistryLocationW; // eax
  int v6; // r8d
  int v7; // r9d
  HANDLE v8; // rax
  unsigned int v9; // ecx
  int v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v12; // [rsp+48h] [rbp+10h] BYREF

  v11 = 0;
  if ( a1 )
  {
    *a1 = 0;
    ProcessHeap = GetProcessHeap();
    v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( v4 )
    {
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                     L"siufregistrystateroot",
                                     L"SOFTWARE\\Microsoft\\Siuf",
                                     v4,
                                     520,
                                     &v11);
      v2 = PersistedRegistryLocationW;
      if ( PersistedRegistryLocationW > 0 )
        v2 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( v2 >= 0 )
      {
        v9 = dword_140027000;
        *a1 = v4;
        if ( v9 > 5 )
        {
          v12 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)byte_140022E9B,
            v6,
            v7,
            (__int64)&v12);
        }
      }
      else
      {
        v8 = GetProcessHeap();
        HeapFree(v8, 0, v4);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140017770  mov     [rsp+arg_10], rbx
0x140017775  mov     [rsp+arg_18], rsi
0x14001777a  push    rdi
0x14001777b  sub     rsp, 30h
0x14001777f  mov     [rsp+38h+arg_0], 0
0x140017787  mov     rsi, rcx
0x14001778a  test    rcx, rcx
0x14001778d  jnz     short loc_140017799
0x14001778f  mov     ebx, 80004003h
0x140017794  jmp     loc_140017841
0x140017799  mov     qword ptr [rcx], 0
0x1400177a0  call    cs:__imp_GetProcessHeap
0x1400177a6  mov     ebx, 208h
0x1400177ab  mov     edx, 8; dwFlags
0x1400177b0  mov     rcx, rax; hHeap
0x1400177b3  mov     r8d, ebx; dwBytes
0x1400177b6  call    cs:__imp_HeapAlloc
0x1400177bc  mov     rdi, rax
0x1400177bf  test    rax, rax
0x1400177c2  jnz     short loc_1400177CB
0x1400177c4  mov     ebx, 8007000Eh
0x1400177c9  jmp     short loc_140017841
0x1400177cb  lea     rax, [rsp+38h+arg_0]
0x1400177d0  mov     r9d, ebx
0x1400177d3  mov     r8, rdi
0x1400177d6  mov     [rsp+38h+var_18], rax
0x1400177db  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Siuf"
0x1400177e2  lea     rcx, aSiufregistryst; "siufregistrystateroot"
0x1400177e9  call    cs:__imp_GetPersistedRegistryLocationW
0x1400177ef  mov     ebx, eax
0x1400177f1  test    eax, eax
0x1400177f3  jle     short loc_1400177FE
0x1400177f5  movzx   ebx, ax
0x1400177f8  or      ebx, 80070000h
0x1400177fe  test    ebx, ebx
0x140017800  jns     short loc_140017818
0x140017802  call    cs:__imp_GetProcessHeap
0x140017808  mov     r8, rdi; lpMem
0x14001780b  xor     edx, edx; dwFlags
0x14001780d  mov     rcx, rax; hHeap
0x140017810  call    cs:__imp_HeapFree
0x140017816  jmp     short loc_140017841
0x140017818  mov     ecx, cs:dword_140027000
0x14001781e  mov     [rsi], rdi
0x140017821  cmp     ecx, 5
0x140017824  jbe     short loc_140017841
0x140017826  lea     rax, [rsp+38h+arg_8]
0x14001782b  mov     [rsp+38h+arg_8], rdi
0x140017830  lea     rdx, byte_140022E9B
0x140017837  mov     [rsp+38h+var_18], rax
0x14001783c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140017841  mov     rsi, [rsp+38h+arg_18]
0x140017846  mov     eax, ebx
0x140017848  mov     rbx, [rsp+38h+arg_10]
0x14001784d  add     rsp, 30h
0x140017851  pop     rdi
0x140017852  retn
```
