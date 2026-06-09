# PSetupGetPathToSearch

- ea: `0x1800211e0`
- end: `0x1800212bb`
- name: `PSetupGetPathToSearch`
- size: `219`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000ce94`
- `0x180017550`
- `0x180018848`
- `0x18001de14`
- `0x18002354c`

## callees

- `0x1800211e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212a8`
- `SETUPAPI!SetupRemoveFromSourceListW` at `0x180021255`
- `SETUPAPI!SetupRemoveFromSourceListW` at `0x180021255`
- `SETUPAPI!SetupPromptForDiskW` at `0x180021245`
- `SETUPAPI!SetupPromptForDiskW` at `0x180021245`

## pseudocode

```c
__int64 __fastcall PSetupGetPathToSearch(
        HWND a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *FileSought,
        int a5,
        PWSTR PathBuffer)
{
  const WCHAR *v6; // rbx
  bool v7; // cf
  UINT v8; // eax
  __int64 v9; // rax
  DWORD v11; // ecx
  DWORD PathRequiredSize; // [rsp+78h] [rbp+20h] BYREF

  v6 = PathBuffer;
  v7 = a5 != 0;
  a5 = -a5;
  PathRequiredSize = 0;
  v8 = SetupPromptForDiskW(
         a1,
         a2,
         a3,
         (PCWSTR)((unsigned __int64)PathBuffer & -(__int64)(*PathBuffer != 0)),
         FileSought,
         0,
         v7 ? 12802 : 514,
         PathBuffer,
         0x104u,
         &PathRequiredSize);
  if ( v8 )
  {
    v11 = 1223;
    if ( v8 - 3 <= 1 )
      v11 = 8;
    SetLastError(v11);
    return 0;
  }
  else
  {
    SetupRemoveFromSourceListW(0x40u, v6);
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    PathRequiredSize = v9;
    if ( v6[(unsigned int)v9 - 1] != 92 && (unsigned int)v9 < 0x102 )
    {
      v6[(unsigned int)v9] = 92;
      v6[PathRequiredSize + 1] = 0;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1800211e0  mov     [rsp+arg_0], rbx
0x1800211e5  push    rdi
0x1800211e6  sub     rsp, 50h
0x1800211ea  mov     rbx, [rsp+58h+arg_28]
0x1800211f2  xor     edi, edi
0x1800211f4  neg     [rsp+58h+arg_20]
0x1800211fb  mov     r11, r9
0x1800211fe  mov     [rsp+58h+arg_18], edi
0x180021202  sbb     r10d, r10d
0x180021205  movzx   eax, word ptr [rbx]
0x180021208  and     r10d, 3000h
0x18002120f  add     r10d, 202h
0x180021216  neg     ax
0x180021219  lea     rax, [rsp+58h+arg_18]
0x18002121e  mov     [rsp+58h+PathRequiredSize], rax; PathRequiredSize
0x180021223  sbb     r9, r9
0x180021226  mov     [rsp+58h+PathBufferSize], 104h; PathBufferSize
0x18002122e  and     r9, rbx; PathToSource
0x180021231  mov     [rsp+58h+PathBuffer], rbx; PathBuffer
0x180021236  mov     [rsp+58h+DiskPromptStyle], r10d; DiskPromptStyle
0x18002123b  mov     [rsp+58h+TagFile], rdi; TagFile
0x180021240  mov     [rsp+58h+FileSought], r11; FileSought
0x180021245  call    cs:__imp_SetupPromptForDiskW
0x18002124b  test    eax, eax
0x18002124d  jnz     short loc_180021296
0x18002124f  mov     rdx, rbx; Source
0x180021252  lea     ecx, [rdi+40h]; Flags
0x180021255  call    cs:__imp_SetupRemoveFromSourceListW
0x18002125b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002125f  inc     rax
0x180021262  cmp     [rbx+rax*2], di
0x180021266  jnz     short loc_18002125F
0x180021268  mov     ecx, eax
0x18002126a  mov     eax, 5Ch ; '\'
0x18002126f  mov     [rsp+58h+arg_18], ecx
0x180021273  cmp     [rbx+rcx*2-2], ax
0x180021278  jz      short loc_18002128F
0x18002127a  cmp     ecx, 102h
0x180021280  jnb     short loc_18002128F
0x180021282  mov     [rbx+rcx*2], ax
0x180021286  mov     ecx, [rsp+58h+arg_18]
0x18002128a  mov     [rbx+rcx*2+2], di
0x18002128f  mov     eax, 1
0x180021294  jmp     short loc_1800212B0
0x180021296  add     eax, 0FFFFFFFDh
0x180021299  mov     ecx, 4C7h
0x18002129e  cmp     eax, 1
0x1800212a1  ja      short loc_1800212A8
0x1800212a3  mov     ecx, 8; dwErrCode
0x1800212a8  call    cs:__imp_SetLastError
0x1800212ae  xor     eax, eax
0x1800212b0  mov     rbx, [rsp+58h+arg_0]
0x1800212b5  add     rsp, 50h
0x1800212b9  pop     rdi
0x1800212ba  retn
```
