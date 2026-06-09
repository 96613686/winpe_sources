# D3DApiWrapper::D3DPERF_SetMarker(ulong,ushort const *)

- ea: `0x18006d1d0`
- end: `0x18006d299`
- name: `?D3DPERF_SetMarker@D3DApiWrapper@@SAXKPEBG@Z`
- size: `201`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006d2a0`
- `0x180071e28`
- `0x180073624`
- `0x180076fb0`

## callees

- `0x18006d1d0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d223`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d223`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d207`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d207`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d277`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d277`

## string_xrefs

- `0x18006d21c`: `d3d9.dll`

## pseudocode

```c
void __fastcall D3DApiWrapper::D3DPERF_SetMarker(unsigned int a1, const unsigned __int16 *a2)
{
  HMODULE Library; // rbx

  if ( !byte_1800C1128 )
  {
    Library = (HMODULE)_InterlockedCompareExchange64((volatile signed __int64 *)&hLibModule, 0, 0);
    if ( !Library )
    {
      EnterCriticalSection(&CriticalSection);
      if ( hLibModule || (Library = LoadLibraryExW(L"d3d9.dll", 0, 0)) != 0 )
      {
        ((void (__fastcall *)(void ***, HMODULE))D3DApiWrapper::m_singletonInstance[1])(
          &D3DApiWrapper::m_singletonInstance,
          Library);
        hLibModule = Library;
      }
      else
      {
        byte_1800C1128 = 1;
      }
      LeaveCriticalSection(&CriticalSection);
    }
  }
  if ( qword_1800C1130 )
    qword_1800C1130(a1, a2);
  else
    SetLastError(0x32u);
}

```

## disassembly

```asm
0x18006d1d0  mov     [rsp+arg_0], rbx
0x18006d1d5  mov     [rsp+arg_8], rsi
0x18006d1da  push    rdi
0x18006d1db  sub     rsp, 20h
0x18006d1df  cmp     cs:byte_1800C1128, 0
0x18006d1e6  mov     rdi, rdx
0x18006d1e9  mov     esi, ecx
0x18006d1eb  jnz     short loc_18006D268
0x18006d1ed  xor     r8d, r8d
0x18006d1f0  xor     eax, eax
0x18006d1f2  lock cmpxchg cs:hLibModule, r8
0x18006d1fb  mov     rbx, rax
0x18006d1fe  jnz     short loc_18006D268
0x18006d200  lea     rcx, CriticalSection; lpCriticalSection
0x18006d207  call    cs:__imp_EnterCriticalSection
0x18006d20d  mov     rdx, cs:hLibModule; hFile
0x18006d214  test    rdx, rdx
0x18006d217  jnz     short loc_18006D23A
0x18006d219  xor     r8d, r8d; dwFlags
0x18006d21c  lea     rcx, aD3d9Dll; "d3d9.dll"
0x18006d223  call    cs:__imp_LoadLibraryExW
0x18006d229  mov     rbx, rax
0x18006d22c  test    rax, rax
0x18006d22f  jnz     short loc_18006D23A
0x18006d231  mov     cs:byte_1800C1128, 1
0x18006d238  jmp     short loc_18006D25B
0x18006d23a  mov     rax, cs:?m_singletonInstance@D3DApiWrapper@@0V1@A; D3DApiWrapper D3DApiWrapper::m_singletonInstance
0x18006d241  lea     rcx, ?m_singletonInstance@D3DApiWrapper@@0V1@A; D3DApiWrapper D3DApiWrapper::m_singletonInstance
0x18006d248  mov     rdx, rbx
0x18006d24b  mov     rax, [rax+8]
0x18006d24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d254  mov     cs:hLibModule, rbx
0x18006d25b  lea     rcx, CriticalSection; lpCriticalSection
0x18006d262  call    cs:__imp_LeaveCriticalSection
0x18006d268  mov     rax, cs:qword_1800C1130
0x18006d26f  test    rax, rax
0x18006d272  jnz     short loc_18006D27F
0x18006d274  lea     ecx, [rax+32h]; dwErrCode
0x18006d277  call    cs:__imp_SetLastError
0x18006d27d  jmp     short loc_18006D289
0x18006d27f  mov     rdx, rdi
0x18006d282  mov     ecx, esi
0x18006d284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d289  mov     rbx, [rsp+28h+arg_0]
0x18006d28e  mov     rsi, [rsp+28h+arg_8]
0x18006d293  add     rsp, 20h
0x18006d297  pop     rdi
0x18006d298  retn
```
