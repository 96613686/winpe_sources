# CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag(void)

- ea: `0x18001b880`
- end: `0x18001b965`
- name: `?GetRASConnectionPropertiesFromPropertyBag@CRASConnectionTestingPage@@IEAAPEAU_RASNCWINFO@@XZ`
- size: `229`
- prototype: `struct _RASNCWINFO *__fastcall(CRASConnectionTestingPage *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b0f0`
- `0x18001ba94`

## callees

- `0x180010c38`
- `0x18001b880`
- `0x180030010`

## import_xrefs

- `RASAPI32!GetPersonalPhonebookPath` at `0x18001b90a`
- `RASAPI32!GetPersonalPhonebookPath` at `0x18001b90a`
- `RASAPI32!GetPublicPhonebookPath` at `0x18001b8f7`
- `RASAPI32!GetPublicPhonebookPath` at `0x18001b8f7`
- `rtutils!TracePrintfExA` at `0x18001b92f`
- `rtutils!TracePrintfExA` at `0x18001b951`
- `rtutils!TracePrintfExA` at `0x18001b92f`
- `rtutils!TracePrintfExA` at `0x18001b951`

## pseudocode

```c
struct _RASNCWINFO *__fastcall CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag(
        CRASConnectionTestingPage *this)
{
  int v2; // eax
  _DWORD *v3; // rbx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64 *, _QWORD))(**((_QWORD **)this + 10) + 48LL))(
         *((_QWORD *)this + 10),
         (char *)this + 44,
         L"RASConnectionDetails",
         &v5,
         0);
  if ( v2 )
  {
    v3 = 0;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "GetRASConnectionPropertiesFromPropertyBag: Failed to get RasConnectionDetails: hr = %#x",
        v2);
  }
  else
  {
    v3 = *(_DWORD **)v5;
    StringCchCopyW((unsigned __int16 *)this + 44, 0x101u, (unsigned __int16 *)(*(_QWORD *)v5 + 1038LL));
    if ( v3[721] )
      GetPublicPhonebookPath((char *)this + 602, 261);
    else
      GetPersonalPhonebookPath(0, (char *)this + 602, 261);
    *((_DWORD *)this + 281) = *v3;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetRASConnectionPropertiesFromPropertyBag: Got RasConnectionDetails");
  }
  return (struct _RASNCWINFO *)v3;
}

```

## disassembly

```asm
0x18001b880  mov     r11, rsp
0x18001b883  mov     [r11+10h], rbx
0x18001b887  push    rdi
0x18001b888  sub     rsp, 30h
0x18001b88c  mov     rdi, rcx
0x18001b88f  mov     qword ptr [r11+8], 0
0x18001b897  mov     rcx, [rcx+50h]
0x18001b89b  lea     r9, [r11+8]
0x18001b89f  lea     r8, aRasconnectiond_3; "RASConnectionDetails"
0x18001b8a6  mov     qword ptr [r11-18h], 0
0x18001b8ae  lea     rdx, [rdi+2Ch]
0x18001b8b2  mov     rax, [rcx]
0x18001b8b5  mov     rax, [rax+30h]
0x18001b8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8be  test    eax, eax
0x18001b8c0  jnz     short loc_18001B937
0x18001b8c2  mov     rax, [rsp+38h+arg_0]
0x18001b8c7  lea     rcx, [rdi+58h]; unsigned __int16 *
0x18001b8cb  mov     edx, 101h; unsigned __int64
0x18001b8d0  mov     rbx, [rax]
0x18001b8d3  lea     r8, [rbx+40Eh]; unsigned __int16 *
0x18001b8da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b8df  cmp     dword ptr [rbx+0B44h], 0
0x18001b8e6  lea     r11, [rdi+25Ah]
0x18001b8ed  jz      short loc_18001B8FF
0x18001b8ef  mov     edx, 105h
0x18001b8f4  mov     rcx, r11
0x18001b8f7  call    cs:__imp_GetPublicPhonebookPath
0x18001b8fd  jmp     short loc_18001B910
0x18001b8ff  mov     r8d, 105h
0x18001b905  mov     rdx, r11
0x18001b908  xor     ecx, ecx
0x18001b90a  call    cs:__imp_GetPersonalPhonebookPath
0x18001b910  mov     eax, [rbx]
0x18001b912  mov     [rdi+464h], eax
0x18001b918  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b91e  cmp     ecx, 0FFFFFFFFh
0x18001b921  jz      short loc_18001B957
0x18001b923  lea     r8, aGetrasconnecti; "GetRASConnectionPropertiesFromPropertyB"...
0x18001b92a  mov     edx, 0Ch; dwFlags
0x18001b92f  call    cs:__imp_TracePrintfExA
0x18001b935  jmp     short loc_18001B957
0x18001b937  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b93d  xor     ebx, ebx
0x18001b93f  cmp     ecx, 0FFFFFFFFh
0x18001b942  jz      short loc_18001B957
0x18001b944  mov     r9d, eax
0x18001b947  lea     r8, aGetrasconnecti_0; "GetRASConnectionPropertiesFromPropertyB"...
0x18001b94e  lea     edx, [rbx+0Ch]; dwFlags
0x18001b951  call    cs:__imp_TracePrintfExA
0x18001b957  mov     rax, rbx
0x18001b95a  mov     rbx, [rsp+38h+arg_8]
0x18001b95f  add     rsp, 30h
0x18001b963  pop     rdi
0x18001b964  retn
```
