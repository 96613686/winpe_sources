# GetThis<CVPNCheckInetConnPage>(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001c174`
- end: `0x18001c1c7`
- name: `??$GetThis@VCVPNCheckInetConnPage@@@@YAPEAVCVPNCheckInetConnPage@@PEAUHWND__@@I_K_J@Z`
- size: `83`
- prototype: `HANDLE __fastcall(HWND, int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c4b0`
- `0x18001c6d0`

## callees

- `0x18001c174`

## import_xrefs

- `USER32!GetPropW` at `0x18001c1b5`
- `USER32!GetPropW` at `0x18001c1b5`
- `USER32!RemovePropW` at `0x18001c1ad`
- `USER32!RemovePropW` at `0x18001c1ad`
- `USER32!SetPropW` at `0x18001c199`
- `USER32!SetPropW` at `0x18001c199`

## pseudocode

```c
HANDLE __fastcall GetThis<CVPNCheckInetConnPage>(HWND a1, int a2, __int64 a3, _QWORD *a4)
{
  void *v4; // rbx

  v4 = a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = (void *)a4[6];
    SetPropW(a1, L"_Win32_this_", v4);
  }
  else if ( a2 == 2 )
  {
    return RemovePropW(a1, L"_Win32_this_");
  }
  else
  {
    return GetPropW(a1, L"_Win32_this_");
  }
  return v4;
}

```

## disassembly

```asm
0x18001c174  push    rbx
0x18001c176  sub     rsp, 20h
0x18001c17a  mov     rbx, r9
0x18001c17d  cmp     edx, 110h
0x18001c183  jnz     short loc_18001C1A1
0x18001c185  cmp     dword ptr [r9], 68h ; 'h'
0x18001c189  jnz     short loc_18001C18F
0x18001c18b  mov     rbx, [r9+30h]
0x18001c18f  mov     r8, rbx; hData
0x18001c192  lea     rdx, aWin32This_7; "_Win32_this_"
0x18001c199  call    cs:__imp_SetPropW
0x18001c19f  jmp     short loc_18001C1BE
0x18001c1a1  cmp     edx, 2
0x18001c1a4  lea     rdx, aWin32This_7; "_Win32_this_"
0x18001c1ab  jnz     short loc_18001C1B5
0x18001c1ad  call    cs:__imp_RemovePropW
0x18001c1b3  jmp     short loc_18001C1BB
0x18001c1b5  call    cs:__imp_GetPropW
0x18001c1bb  mov     rbx, rax
0x18001c1be  mov     rax, rbx
0x18001c1c1  add     rsp, 20h
0x18001c1c5  pop     rbx
0x18001c1c6  retn
```
