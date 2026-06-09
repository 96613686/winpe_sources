# GetFormattedErrorMessage(ushort * *,ulong,...)

- ea: `0x180002e80`
- end: `0x180002fa4`
- name: `?GetFormattedErrorMessage@@YAKPEAPEAGKZZ`
- size: `292`
- prototype: `__int64(unsigned __int16 **, DWORD, ...)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180002170`
- `0x180002fac`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x180004050`
- `0x1800040d0`
- `0x180004370`
- `0x180005ba0`

## callees

- `0x180001318`
- `0x180002e80`
- `0x180006b68`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002f85`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002f85`
- `KERNEL32!FormatMessageW` at `0x180002ef9`
- `KERNEL32!FormatMessageW` at `0x180002ef9`
- `KERNEL32!LocalFree` at `0x180002f93`
- `KERNEL32!LocalFree` at `0x180002f93`

## string_xrefs

- `0x180002ebb`: `pwrshplugin.dll`

## pseudocode

```c
__int64 GetFormattedErrorMessage(unsigned __int16 **a1, DWORD a2, ...)
{
  HINSTANCE MUILibraryW; // rax
  DWORD v5; // eax
  DWORD v6; // esi
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rcx
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-30h] BYREF
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  va_copy(Arguments, va);
  MUILibraryW = (HINSTANCE)g_hResourceInstance;
  *a1 = 0;
  if ( !MUILibraryW )
  {
    MUILibraryW = LoadMUILibraryW(L"pwrshplugin.dll", 8u, 0);
    g_hResourceInstance = MUILibraryW;
  }
  *(_QWORD *)Buffer = 0;
  v5 = FormatMessageW(0x900u, MUILibraryW, a2, 0, Buffer, 0, &Arguments);
  v6 = v5;
  if ( v5 )
  {
    v7 = v5 + 1;
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v7, 2u));
    *a1 = v8;
    if ( v8 )
    {
      if ( v7 )
      {
        if ( v7 <= 0x7FFFFFFF )
        {
          v9 = *(unsigned __int16 **)Buffer;
          v10 = 2147483646;
          do
          {
            if ( !v10 )
              break;
            if ( !*v9 )
              break;
            *v8++ = *v9++;
            --v10;
            --v7;
          }
          while ( v7 );
          v11 = v8 - 1;
          if ( v7 )
            v11 = v8;
          *v11 = 0;
          if ( v7 )
            goto LABEL_16;
        }
        else
        {
          *v8 = 0;
        }
      }
      v6 = 0;
      operator delete[](*a1);
      *a1 = 0;
    }
LABEL_16:
    LocalFree(*(HLOCAL *)Buffer);
  }
  return v6;
}

```

## disassembly

```asm
0x180002e80  mov     rax, rsp
0x180002e83  mov     [rax+10h], edx
0x180002e86  mov     [rax+18h], r8
0x180002e8a  mov     [rax+20h], r9
0x180002e8e  push    rbx
0x180002e8f  push    rbp
0x180002e90  push    rsi
0x180002e91  push    rdi
0x180002e92  sub     rsp, 58h
0x180002e96  lea     rax, [rax+18h]
0x180002e9a  xor     ebp, ebp
0x180002e9c  mov     [rsp+78h+var_30], rax
0x180002ea1  mov     ebx, edx
0x180002ea3  mov     rax, cs:?g_hResourceInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceInstance
0x180002eaa  mov     rdi, rcx
0x180002ead  mov     [rcx], rbp
0x180002eb0  test    rax, rax
0x180002eb3  jnz     short loc_180002ECE
0x180002eb5  xor     r8d, r8d; LangID
0x180002eb8  lea     edx, [rbp+8]; dwLangConvention
0x180002ebb  lea     rcx, LibFileName; "pwrshplugin.dll"
0x180002ec2  call    LoadMUILibraryW
0x180002ec7  mov     cs:?g_hResourceInstance@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceInstance
0x180002ece  lea     rcx, [rsp+78h+var_30]
0x180002ed3  mov     qword ptr [rsp+78h+Buffer], rbp
0x180002ed8  mov     [rsp+78h+Arguments], rcx; Arguments
0x180002edd  xor     r9d, r9d; dwLanguageId
0x180002ee0  lea     rcx, [rsp+78h+Buffer]
0x180002ee5  mov     [rsp+78h+nSize], ebp; nSize
0x180002ee9  mov     [rsp+78h+lpBuffer], rcx; lpBuffer
0x180002eee  mov     r8d, ebx; dwMessageId
0x180002ef1  mov     ecx, 900h; dwFlags
0x180002ef6  mov     rdx, rax; lpSource
0x180002ef9  call    cs:__imp_FormatMessageW
0x180002eff  mov     esi, eax
0x180002f01  test    eax, eax
0x180002f03  jz      loc_180002F99
0x180002f09  lea     ebx, [rax+1]
0x180002f0c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002f13  mov     eax, 2
0x180002f18  mul     rbx
0x180002f1b  cmovb   rax, rcx
0x180002f1f  mov     rcx, rax; unsigned __int64
0x180002f22  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002f27  mov     [rdi], rax
0x180002f2a  test    rax, rax
0x180002f2d  jz      short loc_180002F8E
0x180002f2f  test    rbx, rbx
0x180002f32  jz      short loc_180002F80
0x180002f34  cmp     rbx, 7FFFFFFFh
0x180002f3b  jbe     short loc_180002F42
0x180002f3d  mov     [rax], bp
0x180002f40  jmp     short loc_180002F80
0x180002f42  mov     rdx, qword ptr [rsp+78h+Buffer]
0x180002f47  mov     ecx, 7FFFFFFEh
0x180002f4c  test    rcx, rcx
0x180002f4f  jz      short loc_180002F70
0x180002f51  movzx   r8d, word ptr [rdx]
0x180002f55  test    r8w, r8w
0x180002f59  jz      short loc_180002F70
0x180002f5b  mov     [rax], r8w
0x180002f5f  add     rdx, 2
0x180002f63  add     rax, 2
0x180002f67  dec     rcx
0x180002f6a  sub     rbx, 1
0x180002f6e  jnz     short loc_180002F4C
0x180002f70  test    rbx, rbx
0x180002f73  lea     rcx, [rax-2]
0x180002f77  cmovnz  rcx, rax
0x180002f7b  mov     [rcx], bp
0x180002f7e  jnz     short loc_180002F8E
0x180002f80  mov     rcx, [rdi]
0x180002f83  mov     esi, ebp
0x180002f85  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002f8b  mov     [rdi], rbp
0x180002f8e  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x180002f93  call    cs:__imp_LocalFree
0x180002f99  mov     eax, esi
0x180002f9b  add     rsp, 58h
0x180002f9f  pop     rdi
0x180002fa0  pop     rsi
0x180002fa1  pop     rbp
0x180002fa2  pop     rbx
0x180002fa3  retn
```
