# SetScreenReaderStaticDuckingValue(int)

- ea: `0x18001e010`
- end: `0x18001e09e`
- name: `?SetScreenReaderStaticDuckingValue@@YAJH@Z`
- size: `142`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c10`

## callees

- `0x18001e010`
- `0x18001e0a4`
- `0x1800215f0`
- `0x180023154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e072`

## string_xrefs

- `0x18001e05b`: `ScreenReaderDuckingPreference`

## pseudocode

```c
__int64 __fastcall SetScreenReaderStaticDuckingValue(int a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned int v5; // ebx
  signed int LastError; // eax
  unsigned int v8; // [rsp+20h] [rbp-48h]
  HKEY v9[5]; // [rsp+40h] [rbp-28h] BYREF

  memset(v9, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Create(
                       (ATL::CRegKey *)v9,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Multimedia\\Audio",
                       a4,
                       v8,
                       0x20006u)
    || (v5 = 0, ATL::CRegKey::SetDWORDValue(v9, L"ScreenReaderDuckingPreference", a1)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v9);
  return v5;
}

```

## disassembly

```asm
0x18001e010  mov     rax, rsp
0x18001e013  mov     [rax+8], rbx
0x18001e017  push    rdi
0x18001e018  sub     rsp, 60h
0x18001e01c  mov     edi, ecx
0x18001e01e  mov     qword ptr [rax-28h], 0
0x18001e026  lea     rcx, [rax-28h]; this
0x18001e02a  mov     qword ptr [rax-20h], 0
0x18001e032  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Multimedia\\Audio"
0x18001e039  mov     qword ptr [rax-18h], 0
0x18001e041  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001e048  mov     dword ptr [rax-40h], 20006h
0x18001e04f  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001e054  test    eax, eax
0x18001e056  jnz     short loc_18001E072
0x18001e058  mov     r8d, edi; unsigned int
0x18001e05b  lea     rdx, aScreenreaderdu; "ScreenReaderDuckingPreference"
0x18001e062  lea     rcx, [rsp+68h+var_28]; this
0x18001e067  xor     ebx, ebx
0x18001e069  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001e06e  test    eax, eax
0x18001e070  jz      short loc_18001E087
0x18001e072  call    cs:__imp_GetLastError
0x18001e078  mov     ebx, eax
0x18001e07a  test    eax, eax
0x18001e07c  jle     short loc_18001E087
0x18001e07e  movzx   ebx, ax
0x18001e081  or      ebx, 80070000h
0x18001e087  lea     rcx, [rsp+68h+var_28]; this
0x18001e08c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001e091  mov     eax, ebx
0x18001e093  mov     rbx, [rsp+68h+arg_0]
0x18001e098  add     rsp, 60h
0x18001e09c  pop     rdi
0x18001e09d  retn
```
