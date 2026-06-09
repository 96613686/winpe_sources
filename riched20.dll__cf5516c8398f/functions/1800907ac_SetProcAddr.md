# SetProcAddr

- ea: `0x1800907ac`
- end: `0x1800908a1`
- name: `SetProcAddr`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `48`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180040178`
- `0x180041150`
- `0x18004a23c`
- `0x18004b168`
- `0x1800532ec`
- `0x18005361c`
- `0x180053d4c`
- `0x180055f28`
- `0x18005afc8`
- `0x18005c250`
- `0x180062130`
- `0x1800622a0`
- `0x18006bf10`
- `0x18006f94c`
- `0x180074458`
- `0x18007c360`
- `0x18007cb94`
- `0x18007d7bc`
- `0x18007da2c`
- `0x18008c2dc`
- `0x18008cf08`
- `0x18008cfc0`
- `0x18008d5ac`
- `0x18008d624`
- `0x18008f770`
- `0x18008f924`
- `0x18008fbd0`
- `0x18008fc64`
- `0x18008fcfc`
- `0x18008fd94`
- `0x18008fdf0`
- `0x18008fe40`
- `0x18008fe9c`
- `0x18008fef8`
- `0x18008ff64`
- `0x18008ffc8`
- `0x180090024`
- `0x180090068`
- `0x18009049c`
- `0x180090508`
- `0x180090564`
- `0x180090c0c`
- `0x180090c5c`
- `0x180090cac`
- `0x180090cf8`
- `0x180090ed4`
- `0x180090f20`
- `0x180090f8c`

## callees

- `0x18008f8b0`
- `0x1800907ac`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800907ca`
- `KERNEL32!EnterCriticalSection` at `0x1800907ca`
- `KERNEL32!LeaveCriticalSection` at `0x18009089a`
- `KERNEL32!GetProcAddress` at `0x18009087b`
- `KERNEL32!GetProcAddress` at `0x18009087b`

## string_xrefs

- `0x180090862`: `oleaut32.dll`
- `0x180090841`: `ole32.dll`
- `0x180090820`: `oleacc.dll`
- `0x1800907ff`: `user32.dll`

## pseudocode

```c
void __fastcall SetProcAddr(FARPROC *a1, int a2, const CHAR *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // r8d
  HMODULE v8; // rcx
  int v9; // ebx
  int v10; // ebx
  HINSTANCE Library; // rax

  EnterCriticalSection(&g_CriticalSection);
  if ( !*a1 )
  {
    v8 = 0;
    if ( a2 )
    {
      v9 = a2 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            goto LABEL_15;
          v8 = (HMODULE)qword_1800A44E8;
          if ( qword_1800A44E8 )
            goto LABEL_15;
          Library = CW32System::LoadLibrary(L"user32.dll", v6, v7);
          qword_1800A44E8 = (__int64)Library;
          goto LABEL_14;
        }
        v8 = (HMODULE)qword_1800A4488;
        if ( !qword_1800A4488 )
        {
          Library = CW32System::LoadLibrary(L"oleacc.dll", v6, v7);
          qword_1800A4488 = (__int64)Library;
LABEL_14:
          v8 = Library;
        }
      }
      else
      {
        v8 = qword_1800A4478;
        if ( !qword_1800A4478 )
        {
          Library = CW32System::LoadLibrary(L"ole32.dll", v6, v7);
          qword_1800A4478 = Library;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v8 = hLibModule;
      if ( !hLibModule )
      {
        Library = CW32System::LoadLibrary(L"oleaut32.dll", v6, v7);
        hLibModule = Library;
        goto LABEL_14;
      }
    }
LABEL_15:
    *a1 = GetProcAddress(v8, a3);
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x1800907ac  mov     [rsp+arg_0], rbx
0x1800907b1  mov     [rsp+arg_8], rsi
0x1800907b6  push    rdi
0x1800907b7  sub     rsp, 20h
0x1800907bb  mov     rdi, rcx
0x1800907be  mov     rsi, r8
0x1800907c1  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800907c8  mov     ebx, edx
0x1800907ca  call    cs:__imp_EnterCriticalSection
0x1800907d0  cmp     qword ptr [rdi], 0
0x1800907d4  jnz     loc_180090884
0x1800907da  xor     ecx, ecx
0x1800907dc  test    ebx, ebx
0x1800907de  jz      short loc_180090856
0x1800907e0  sub     ebx, 1
0x1800907e3  jz      short loc_180090835
0x1800907e5  sub     ebx, 1
0x1800907e8  jz      short loc_180090814
0x1800907ea  cmp     ebx, 1
0x1800907ed  jnz     loc_180090878
0x1800907f3  mov     rcx, cs:qword_1800A44E8
0x1800907fa  test    rcx, rcx
0x1800907fd  jnz     short loc_180090878
0x1800907ff  lea     rcx, aUser32Dll_0; "user32.dll"
0x180090806  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18009080b  mov     cs:qword_1800A44E8, rax
0x180090812  jmp     short loc_180090875
0x180090814  mov     rcx, cs:qword_1800A4488
0x18009081b  test    rcx, rcx
0x18009081e  jnz     short loc_180090878
0x180090820  lea     rcx, aOleaccDll; "oleacc.dll"
0x180090827  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18009082c  mov     cs:qword_1800A4488, rax
0x180090833  jmp     short loc_180090875
0x180090835  mov     rcx, cs:qword_1800A4478
0x18009083c  test    rcx, rcx
0x18009083f  jnz     short loc_180090878
0x180090841  lea     rcx, aOle32Dll; "ole32.dll"
0x180090848  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18009084d  mov     cs:qword_1800A4478, rax
0x180090854  jmp     short loc_180090875
0x180090856  mov     rcx, cs:hLibModule
0x18009085d  test    rcx, rcx
0x180090860  jnz     short loc_180090878
0x180090862  lea     rcx, aOleaut32Dll; "oleaut32.dll"
0x180090869  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18009086e  mov     cs:hLibModule, rax
0x180090875  mov     rcx, rax; hModule
0x180090878  mov     rdx, rsi; lpProcName
0x18009087b  call    cs:__imp_GetProcAddress
0x180090881  mov     [rdi], rax
0x180090884  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x18009088b  mov     rbx, [rsp+28h+arg_0]
0x180090890  mov     rsi, [rsp+28h+arg_8]
0x180090895  add     rsp, 20h
0x180090899  pop     rdi
0x18009089a  jmp     cs:__imp_LeaveCriticalSection
```
