# CRegistryListener::Register(ushort const *,HWND__ *)

- ea: `0x14001c940`
- end: `0x14001ca9e`
- name: `?Register@CRegistryListener@@QEAAJPEBGPEAUHWND__@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CRegistryListener *__hidden this, const unsigned __int16 *, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007f54`

## callees

- `0x140005b04`
- `0x140007e90`
- `0x140009ca0`
- `0x140009cd8`
- `0x14001c6e8`
- `0x14001c940`
- `0x14001cc50`
- `0x140025d42`

## import_xrefs

- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001ca4e`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001ca4e`
- `KERNEL32!GetLastError` at `0x14001ca81`
- `KERNEL32!GetLastError` at `0x14001ca81`
- `KERNEL32!CreateThread` at `0x14001ca77`
- `KERNEL32!CreateThread` at `0x14001ca77`
- `KERNEL32!CreateEventW` at `0x14001ca04`
- `KERNEL32!CreateEventW` at `0x14001ca04`
- `msvcrt!memmove_s` at `0x14001c9ad`
- `msvcrt!memmove_s` at `0x14001c9ad`

## pseudocode

```c
signed int __fastcall CRegistryListener::Register(CRegistryListener *this, const unsigned __int16 *a2, HWND a3)
{
  signed int result; // eax
  _QWORD *v6; // rdi
  unsigned int v7; // ebp
  int v8; // esi
  unsigned int v9; // esi
  char *Buffer; // rax
  errno_t v11; // eax
  const wchar_t *v12; // rax
  HANDLE EventW; // rax

  if ( !a3 )
    return -2147024809;
  v6 = (_QWORD *)((char *)this + 64);
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 64, L"Software\\Microsoft\\Osk", 22);
  v7 = 19;
  v8 = *(_DWORD *)(*v6 - 16LL);
  if ( v8 >= 19 )
    goto LABEL_6;
  if ( v8 > 0 )
  {
    v7 = *(_DWORD *)(*v6 - 16LL);
LABEL_6:
    v9 = v8 - v7;
    Buffer = (char *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v6);
    v11 = memmove_s(Buffer, 2LL * (int)(v9 + 1), &Buffer[2 * v7], 2LL * (int)(v9 + 1));
    ATL::AtlCrtErrorCheck(v11);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(v6, v9);
  }
  v12 = (const wchar_t *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v6);
  if ( !wcscmp_0(v12, L"ScreenMagnifier") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(v6, L"magnifierpane", 13);
  CRegistryListener::_CopyToSessionKey(this);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  *(_BYTE *)this = 0;
  *((_QWORD *)this + 6) = a3;
  if ( EventW
    && !(unsigned int)ATL::CRegKey::Open(
                        (CRegistryListener *)((char *)this + 8),
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Osk",
                        0x10u)
    && !RegNotifyChangeKeyValue(*((HKEY *)this + 1), 1, 5u, *((HANDLE *)this + 4), 1) )
  {
    *((_QWORD *)this + 5) = CreateThread(0, 0, CRegistryListener::s_ThreadProc, this, 0, (LPDWORD)this + 14);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001c940  push    rbx
0x14001c942  push    rbp
0x14001c943  push    rsi
0x14001c944  push    rdi
0x14001c945  push    r14
0x14001c947  sub     rsp, 30h
0x14001c94b  mov     r14, r8
0x14001c94e  mov     rbx, rcx
0x14001c951  test    r8, r8
0x14001c954  jnz     short loc_14001C960
0x14001c956  mov     eax, 80070057h
0x14001c95b  jmp     loc_14001CA93
0x14001c960  lea     rdi, [rcx+40h]
0x14001c964  mov     r8d, 16h
0x14001c96a  mov     rcx, rdi
0x14001c96d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Osk"
0x14001c974  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c979  mov     rax, [rdi]
0x14001c97c  mov     ebp, 13h
0x14001c981  mov     esi, [rax-10h]
0x14001c984  cmp     esi, ebp
0x14001c986  jge     short loc_14001C98E
0x14001c988  test    esi, esi
0x14001c98a  jle     short loc_14001C9C4
0x14001c98c  mov     ebp, esi
0x14001c98e  mov     rcx, rdi
0x14001c991  sub     esi, ebp
0x14001c993  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x14001c998  lea     ecx, [rsi+1]
0x14001c99b  movsxd  rdx, ecx
0x14001c99e  mov     ecx, ebp
0x14001c9a0  add     rdx, rdx; DestinationSize
0x14001c9a3  mov     r9, rdx; SourceSize
0x14001c9a6  lea     r8, [rax+rcx*2]; Source
0x14001c9aa  mov     rcx, rax; Destination
0x14001c9ad  call    cs:__imp_memmove_s
0x14001c9b3  mov     ecx, eax; int
0x14001c9b5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14001c9ba  mov     edx, esi
0x14001c9bc  mov     rcx, rdi
0x14001c9bf  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x14001c9c4  mov     rcx, rdi
0x14001c9c7  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x14001c9cc  mov     rcx, rax; String1
0x14001c9cf  lea     rdx, aScreenmagnifie; "ScreenMagnifier"
0x14001c9d6  call    wcscmp_0
0x14001c9db  test    eax, eax
0x14001c9dd  jnz     short loc_14001C9F2
0x14001c9df  lea     r8d, [rax+0Dh]
0x14001c9e3  mov     rcx, rdi
0x14001c9e6  lea     rdx, aMagnifierpane; "magnifierpane"
0x14001c9ed  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c9f2  mov     rcx, rbx; this
0x14001c9f5  call    ?_CopyToSessionKey@CRegistryListener@@AEAAXXZ; CRegistryListener::_CopyToSessionKey(void)
0x14001c9fa  xor     r9d, r9d; lpName
0x14001c9fd  xor     r8d, r8d; bInitialState
0x14001ca00  xor     edx, edx; bManualReset
0x14001ca02  xor     ecx, ecx; lpEventAttributes
0x14001ca04  call    cs:__imp_CreateEventW
0x14001ca0a  mov     [rbx+20h], rax
0x14001ca0e  mov     byte ptr [rbx], 0
0x14001ca11  mov     [rbx+30h], r14
0x14001ca15  test    rax, rax
0x14001ca18  jz      short loc_14001CA81
0x14001ca1a  mov     r9d, 10h; unsigned int
0x14001ca20  lea     r8, aSoftwareMicros_7; "Software\\Microsoft\\Osk"
0x14001ca27  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001ca2e  lea     rcx, [rbx+8]; this
0x14001ca32  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ca37  test    eax, eax
0x14001ca39  jnz     short loc_14001CA81
0x14001ca3b  mov     r9, [rbx+20h]; hEvent
0x14001ca3f  lea     edx, [rax+1]; bWatchSubtree
0x14001ca42  mov     rcx, [rbx+8]; hKey
0x14001ca46  lea     r8d, [rax+5]; dwNotifyFilter
0x14001ca4a  mov     [rsp+58h+fAsynchronous], edx; fAsynchronous
0x14001ca4e  call    cs:__imp_RegNotifyChangeKeyValue
0x14001ca54  test    eax, eax
0x14001ca56  jnz     short loc_14001CA81
0x14001ca58  lea     rax, [rbx+38h]
0x14001ca5c  mov     r9, rbx; lpParameter
0x14001ca5f  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x14001ca64  lea     r8, ?s_ThreadProc@CRegistryListener@@CAKPEAX@Z; lpStartAddress
0x14001ca6b  xor     edx, edx; dwStackSize
0x14001ca6d  mov     [rsp+58h+fAsynchronous], 0; dwCreationFlags
0x14001ca75  xor     ecx, ecx; lpThreadAttributes
0x14001ca77  call    cs:__imp_CreateThread
0x14001ca7d  mov     [rbx+28h], rax
0x14001ca81  call    cs:__imp_GetLastError
0x14001ca87  test    eax, eax
0x14001ca89  jle     short loc_14001CA93
0x14001ca8b  movzx   eax, ax
0x14001ca8e  or      eax, 80070000h
0x14001ca93  add     rsp, 30h
0x14001ca97  pop     r14
0x14001ca99  pop     rdi
0x14001ca9a  pop     rsi
0x14001ca9b  pop     rbp
0x14001ca9c  pop     rbx
0x14001ca9d  retn
```
