# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x18002f950`
- end: `0x18002fa7d`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `301`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019f40`
- `0x180028710`
- `0x180029530`
- `0x180029f50`

## callees

- `0x1800080ec`
- `0x180008178`
- `0x18002f950`
- `0x180032010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x18002f9af`
- `ntdll!WinSqmAddToStream` at `0x18002f9af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fa4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fa4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f9ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f9ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f9d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f9d7`
- `USER32!SetCursor` at `0x18002f970`
- `USER32!SetCursor` at `0x18002fa6c`
- `USER32!SetCursor` at `0x18002f970`
- `USER32!SetCursor` at `0x18002fa6c`
- `USER32!LoadCursorW` at `0x18002f967`
- `USER32!LoadCursorW` at `0x18002f967`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v4; // rsi
  bool v5; // zf
  HRESULT v6; // ebx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int v9; // r11d
  int v11; // [rsp+30h] [rbp-38h] BYREF
  const unsigned __int16 *v12; // [rsp+38h] [rbp-30h]
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  ppv = a1;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v4 = SetCursor(CursorW);
  if ( a2 )
  {
    v5 = *a2 == 0;
    v11 = 2;
    if ( v5 )
      a2 = L"(null)";
    v12 = a2;
    WinSqmAddToStream(0, 911, 1, &v11);
  }
  ppv = 0;
  v6 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v6 >= 0 )
  {
    v7 = (unsigned __int16 *)LocalAlloc(0, 0x74u);
    v8 = v7;
    if ( v7 )
    {
      v6 = StringCchCopyW(v7, 0x3Au, L"mshelp://windows/?id=");
      if ( v6 >= 0 )
      {
        v6 = StringCchCatW(v8, v9, L"f12788e4-8405-4cc2-b363-b76b71b01a20");
        if ( v6 >= 0 )
          v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v8);
      }
      LocalFree(v8);
    }
    else
    {
      v6 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002f950  mov     [rsp+arg_0], rcx
0x18002f955  push    rbx
0x18002f956  push    rbp
0x18002f957  push    rsi
0x18002f958  push    rdi
0x18002f959  sub     rsp, 48h
0x18002f95d  mov     rbx, rdx
0x18002f960  xor     ecx, ecx; hInstance
0x18002f962  mov     edx, 7F02h; lpCursorName
0x18002f967  call    cs:__imp_LoadCursorW
0x18002f96d  mov     rcx, rax; hCursor
0x18002f970  call    cs:__imp_SetCursor
0x18002f976  xor     ebp, ebp
0x18002f978  mov     edi, 1
0x18002f97d  mov     rsi, rax
0x18002f980  test    rbx, rbx
0x18002f983  jz      short loc_18002F9B5
0x18002f985  cmp     [rbx], bp
0x18002f988  lea     rax, aNull; "(null)"
0x18002f98f  lea     r9, [rsp+68h+var_38]
0x18002f994  mov     [rsp+68h+var_38], 2
0x18002f99c  cmovz   rbx, rax
0x18002f9a0  mov     r8d, edi
0x18002f9a3  xor     ecx, ecx
0x18002f9a5  mov     [rsp+68h+var_30], rbx
0x18002f9aa  mov     edx, 38Fh
0x18002f9af  call    cs:__imp_WinSqmAddToStream
0x18002f9b5  lea     rax, [rsp+68h+arg_0]
0x18002f9ba  mov     [rsp+68h+arg_0], rbp
0x18002f9bf  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18002f9c6  mov     [rsp+68h+ppv], rax; ppv
0x18002f9cb  mov     r8d, edi; dwClsContext
0x18002f9ce  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18002f9d5  xor     edx, edx; pUnkOuter
0x18002f9d7  call    cs:__imp_CoCreateInstance
0x18002f9dd  mov     ebx, eax
0x18002f9df  test    eax, eax
0x18002f9e1  js      loc_18002FA69
0x18002f9e7  mov     edx, 74h ; 't'; uBytes
0x18002f9ec  xor     ecx, ecx; uFlags
0x18002f9ee  call    cs:__imp_LocalAlloc
0x18002f9f4  mov     rdi, rax
0x18002f9f7  test    rax, rax
0x18002f9fa  jz      short loc_18002FA53
0x18002f9fc  mov     r11d, 3Ah ; ':'
0x18002fa02  lea     r8, aMshelpWindowsI_0; "mshelp://windows/?id="
0x18002fa09  mov     edx, r11d; unsigned __int64
0x18002fa0c  mov     rcx, rax; unsigned __int16 *
0x18002fa0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fa14  mov     ebx, eax
0x18002fa16  test    eax, eax
0x18002fa18  js      short loc_18002FA48
0x18002fa1a  lea     r8, aF12788e484054c; "f12788e4-8405-4cc2-b363-b76b71b01a20"
0x18002fa21  mov     edx, r11d; unsigned __int64
0x18002fa24  mov     rcx, rdi; unsigned __int16 *
0x18002fa27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fa2c  mov     ebx, eax
0x18002fa2e  test    eax, eax
0x18002fa30  js      short loc_18002FA48
0x18002fa32  mov     rcx, [rsp+68h+arg_0]
0x18002fa37  mov     rdx, rdi
0x18002fa3a  mov     rax, [rcx]
0x18002fa3d  mov     rax, [rax+18h]
0x18002fa41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa46  mov     ebx, eax
0x18002fa48  mov     rcx, rdi; hMem
0x18002fa4b  call    cs:__imp_LocalFree
0x18002fa51  jmp     short loc_18002FA58
0x18002fa53  mov     ebx, 8007000Eh
0x18002fa58  mov     rcx, [rsp+68h+arg_0]
0x18002fa5d  mov     rax, [rcx]
0x18002fa60  mov     rax, [rax+10h]
0x18002fa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa69  mov     rcx, rsi; hCursor
0x18002fa6c  call    cs:__imp_SetCursor
0x18002fa72  mov     eax, ebx
0x18002fa74  add     rsp, 48h
0x18002fa78  pop     rdi
0x18002fa79  pop     rsi
0x18002fa7a  pop     rbp
0x18002fa7b  pop     rbx
0x18002fa7c  retn
```
