# GetStateSeparatedSiufMachineRegRoot(ushort * *)

- ea: `0x1400155a8`
- end: `0x1400156ad`
- name: `?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005100`
- `0x140005420`
- `0x14000588c`
- `0x14000784c`
- `0x1400156b4`

## callees

- `0x140001d80`
- `0x1400155a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400155f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400155f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001564f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001564f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015663`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015663`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x140015630`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x140015630`

## string_xrefs

- `0x140015629`: `siufregistrystateroot`

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
        v9 = dword_140028000;
        *a1 = v4;
        if ( v9 > 5 )
        {
          v12 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v9,
            (unsigned int)byte_140023EA3,
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
0x1400155a8  mov     [rsp+arg_10], rbx
0x1400155ad  mov     [rsp+arg_18], rsi
0x1400155b2  push    rdi
0x1400155b3  sub     rsp, 30h
0x1400155b7  mov     [rsp+38h+arg_0], 0
0x1400155bf  mov     rsi, rcx
0x1400155c2  test    rcx, rcx
0x1400155c5  jnz     short loc_1400155D1
0x1400155c7  mov     ebx, 80004003h
0x1400155cc  jmp     loc_14001569A
0x1400155d1  mov     qword ptr [rcx], 0
0x1400155d8  call    cs:__imp_GetProcessHeap
0x1400155df  nop     dword ptr [rax+rax+00h]
0x1400155e4  mov     ebx, 208h
0x1400155e9  mov     edx, 8; dwFlags
0x1400155ee  mov     rcx, rax; hHeap
0x1400155f1  mov     r8d, ebx; dwBytes
0x1400155f4  call    cs:__imp_HeapAlloc
0x1400155fb  nop     dword ptr [rax+rax+00h]
0x140015600  mov     rdi, rax
0x140015603  test    rax, rax
0x140015606  jnz     short loc_140015612
0x140015608  mov     ebx, 8007000Eh
0x14001560d  jmp     loc_14001569A
0x140015612  lea     rax, [rsp+38h+arg_0]
0x140015617  mov     r9d, ebx
0x14001561a  mov     r8, rdi
0x14001561d  mov     [rsp+38h+var_18], rax
0x140015622  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Siuf"
0x140015629  lea     rcx, aSiufregistryst; "siufregistrystateroot"
0x140015630  call    cs:__imp_GetPersistedRegistryLocationW
0x140015637  nop     dword ptr [rax+rax+00h]
0x14001563c  mov     ebx, eax
0x14001563e  test    eax, eax
0x140015640  jle     short loc_14001564B
0x140015642  movzx   ebx, ax
0x140015645  or      ebx, 80070000h
0x14001564b  test    ebx, ebx
0x14001564d  jns     short loc_140015671
0x14001564f  call    cs:__imp_GetProcessHeap
0x140015656  nop     dword ptr [rax+rax+00h]
0x14001565b  mov     r8, rdi; lpMem
0x14001565e  xor     edx, edx; dwFlags
0x140015660  mov     rcx, rax; hHeap
0x140015663  call    cs:__imp_HeapFree
0x14001566a  nop     dword ptr [rax+rax+00h]
0x14001566f  jmp     short loc_14001569A
0x140015671  mov     ecx, cs:dword_140028000
0x140015677  mov     [rsi], rdi
0x14001567a  cmp     ecx, 5
0x14001567d  jbe     short loc_14001569A
0x14001567f  lea     rax, [rsp+38h+arg_8]
0x140015684  mov     [rsp+38h+arg_8], rdi
0x140015689  lea     rdx, byte_140023EA3
0x140015690  mov     [rsp+38h+var_18], rax
0x140015695  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14001569a  mov     rsi, [rsp+38h+arg_18]
0x14001569f  mov     eax, ebx
0x1400156a1  mov     rbx, [rsp+38h+arg_10]
0x1400156a6  add     rsp, 30h
0x1400156aa  pop     rdi
0x1400156ab  retn
```
