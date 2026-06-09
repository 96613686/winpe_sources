# CIsMicrosoftDllCache::Fetch(ushort const *,int *)

- ea: `0x180017ee4`
- end: `0x180018112`
- name: `?Fetch@CIsMicrosoftDllCache@@QEAAJPEBGPEAH@Z`
- size: `558`
- prototype: `__int64 __fastcall(CIsMicrosoftDllCache *this, WCHAR *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c8b8`

## callees

- `0x180017e00`
- `0x180017ee4`
- `0x180018154`
- `0x1800222d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001801a`
- `msvcrt!swprintf_s` at `0x18001801a`
- `msvcrt!_wcsupr` at `0x180018073`
- `msvcrt!_wcsupr` at `0x180018073`
- `msvcrt!wcsncpy_s` at `0x180018060`
- `msvcrt!wcsncpy_s` at `0x180018060`
- `msvcrt!wcsstr` at `0x180018085`
- `msvcrt!wcsstr` at `0x180018085`
- `KERNEL32!HeapFree` at `0x1800180c9`
- `KERNEL32!HeapFree` at `0x1800180c9`
- `KERNEL32!GetProcessHeap` at `0x180017f69`
- `KERNEL32!GetProcessHeap` at `0x1800180bb`
- `KERNEL32!GetProcessHeap` at `0x180017f69`
- `KERNEL32!GetProcessHeap` at `0x1800180bb`
- `KERNEL32!HeapAlloc` at `0x180017f77`
- `KERNEL32!HeapAlloc` at `0x180017f77`
- `VERSION!GetFileVersionInfoW` at `0x180017f99`
- `VERSION!GetFileVersionInfoW` at `0x180017f99`
- `VERSION!VerQueryValueW` at `0x180017fbb`
- `VERSION!VerQueryValueW` at `0x180018035`
- `VERSION!VerQueryValueW` at `0x180017fbb`
- `VERSION!VerQueryValueW` at `0x180018035`
- `VERSION!GetFileVersionInfoSizeW` at `0x180017f59`
- `VERSION!GetFileVersionInfoSizeW` at `0x180017f59`

## string_xrefs

- `0x180018006`: `\StringFileInfo\%04x%04x\CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIsMicrosoftDllCache::Fetch(CIsMicrosoftDllCache *this, WCHAR *a2, int *a3)
{
  CIsMicrosoftDllCache *v5; // rcx
  void *v6; // rbx
  DWORD FileVersionInfoSizeW; // esi
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  unsigned int v10; // esi
  unsigned int v11; // eax
  HANDLE v12; // rax
  __int64 v14; // [rsp+20h] [rbp-488h]
  int v15; // [rsp+30h] [rbp-478h] BYREF
  unsigned int puLen; // [rsp+34h] [rbp-474h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-470h] BYREF
  unsigned int v18; // [rsp+3Ch] [rbp-46Ch]
  DWORD dwHandle; // [rsp+40h] [rbp-468h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-460h] BYREF
  wchar_t *Source; // [rsp+50h] [rbp-458h] BYREF
  void *v22; // [rsp+58h] [rbp-450h]
  WCHAR *v23; // [rsp+60h] [rbp-448h]
  int *v24; // [rsp+68h] [rbp-440h]
  wchar_t Destination[256]; // [rsp+70h] [rbp-438h] BYREF
  wchar_t Buffer[256]; // [rsp+270h] [rbp-238h] BYREF

  v23 = a2;
  v24 = a3;
  v15 = 0;
  if ( (unsigned int)CLruCache::Fetch((CLruCache *)&g_IsMicrosoftDllCache, a2, &v15, 4u) )
  {
    v6 = 0;
    v22 = 0;
    dwHandle = 0;
    puLen = 0;
    lpBuffer = 0;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(a2, &dwHandle);
    if ( FileVersionInfoSizeW )
    {
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, FileVersionInfoSizeW);
      v6 = v9;
      v22 = v9;
      if ( v9 )
      {
        if ( GetFileVersionInfoW(a2, 0, FileVersionInfoSizeW, v9)
          && VerQueryValueW(v6, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          Source = 0;
          v17 = 0;
          v10 = 0;
          v18 = 0;
          while ( v10 < puLen >> 2 )
          {
            LODWORD(v14) = *((unsigned __int16 *)lpBuffer + 2 * v10 + 1);
            swprintf_s(
              Buffer,
              0x100u,
              L"\\StringFileInfo\\%04x%04x\\CompanyName",
              *((unsigned __int16 *)lpBuffer + 2 * v10),
              v14);
            if ( VerQueryValueW(v6, Buffer, (LPVOID *)&Source, &v17) )
            {
              v11 = v17 + 1;
              if ( v17 + 1 > 0xFF )
                v11 = 255;
              wcsncpy_s(Destination, 0x100u, Source, v11);
              Destination[255] = 0;
              _wcsupr(Destination);
              if ( wcsstr(Destination, L"MICROSOFT") )
              {
                v15 = 1;
                break;
              }
            }
            v18 = ++v10;
          }
        }
      }
    }
    if ( v6 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v6);
    }
  }
  if ( a3 )
    *a3 = v15;
  CIsMicrosoftDllCache::_Add(v5, a2, v15);
  return 0;
}

```

## disassembly

```asm
0x180017ee4  mov     [rsp+arg_0], rbx
0x180017ee9  push    rsi
0x180017eea  push    rdi
0x180017eeb  push    r13
0x180017eed  push    r14
0x180017eef  push    r15
0x180017ef1  sub     rsp, 480h
0x180017ef8  mov     rax, cs:__security_cookie
0x180017eff  xor     rax, rsp
0x180017f02  mov     [rsp+4A8h+var_38], rax
0x180017f0a  mov     r15, r8
0x180017f0d  mov     r14, rdx
0x180017f10  mov     [rsp+4A8h+var_448], rdx
0x180017f15  mov     [rsp+4A8h+var_440], r8
0x180017f1a  xor     edi, edi
0x180017f1c  mov     [rsp+4A8h+var_478], edi
0x180017f20  lea     r9d, [rdi+4]; unsigned int
0x180017f24  lea     r8, [rsp+4A8h+var_478]; void *
0x180017f29  lea     rcx, ?g_IsMicrosoftDllCache@@3VCIsMicrosoftDllCache@@A; this
0x180017f30  call    ?Fetch@CLruCache@@UEAAJPEAX0K@Z; CLruCache::Fetch(void *,void *,ulong)
0x180017f35  test    eax, eax
0x180017f37  jz      loc_1800180CF
0x180017f3d  mov     ebx, edi
0x180017f3f  mov     [rsp+4A8h+var_450], rbx
0x180017f44  mov     [rsp+4A8h+dwHandle], edi
0x180017f48  mov     [rsp+4A8h+puLen], edi
0x180017f4c  mov     [rsp+4A8h+lpBuffer], rdi
0x180017f51  lea     rdx, [rsp+4A8h+dwHandle]; lpdwHandle
0x180017f56  mov     rcx, r14; lptstrFilename
0x180017f59  call    cs:__imp_GetFileVersionInfoSizeW
0x180017f5f  mov     esi, eax
0x180017f61  test    eax, eax
0x180017f63  jz      loc_1800180A5
0x180017f69  call    cs:__imp_GetProcessHeap
0x180017f6f  mov     rcx, rax; hHeap
0x180017f72  mov     r8d, esi; dwBytes
0x180017f75  xor     edx, edx; dwFlags
0x180017f77  call    cs:__imp_HeapAlloc
0x180017f7d  mov     rbx, rax
0x180017f80  mov     [rsp+4A8h+var_450], rax
0x180017f85  test    rax, rax
0x180017f88  jz      loc_1800180A5
0x180017f8e  mov     r9, rax; lpData
0x180017f91  mov     r8d, esi; dwLen
0x180017f94  xor     edx, edx; dwHandle
0x180017f96  mov     rcx, r14; lptstrFilename
0x180017f99  call    cs:__imp_GetFileVersionInfoW
0x180017f9f  test    eax, eax
0x180017fa1  jz      loc_1800180A5
0x180017fa7  lea     r9, [rsp+4A8h+puLen]; puLen
0x180017fac  lea     r8, [rsp+4A8h+lpBuffer]; lplpBuffer
0x180017fb1  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x180017fb8  mov     rcx, rbx; pBlock
0x180017fbb  call    cs:__imp_VerQueryValueW
0x180017fc1  test    eax, eax
0x180017fc3  jz      loc_1800180A5
0x180017fc9  mov     [rsp+4A8h+Source], rdi
0x180017fce  mov     [rsp+4A8h+var_470], edi
0x180017fd2  mov     [rsp+4A8h+var_46C], edi
0x180017fd6  mov     esi, edi
0x180017fd8  mov     [rsp+4A8h+var_46C], edi
0x180017fdc  mov     r13d, 0FFh
0x180017fe2  mov     eax, [rsp+4A8h+puLen]
0x180017fe6  shr     eax, 2
0x180017fe9  cmp     esi, eax
0x180017feb  jnb     loc_1800180A5
0x180017ff1  mov     edx, esi
0x180017ff3  mov     rcx, [rsp+4A8h+lpBuffer]
0x180017ff8  movzx   eax, word ptr [rcx+rdx*4+2]
0x180017ffd  movzx   r9d, word ptr [rcx+rdx*4]
0x180018002  mov     [rsp+4A8h+var_488], eax
0x180018006  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\CompanyName"
0x18001800d  mov     edx, 100h; BufferCount
0x180018012  lea     rcx, [rsp+4A8h+Buffer]; Buffer
0x18001801a  call    cs:__imp_swprintf_s
0x180018020  lea     r9, [rsp+4A8h+var_470]; puLen
0x180018025  lea     r8, [rsp+4A8h+Source]; lplpBuffer
0x18001802a  lea     rdx, [rsp+4A8h+Buffer]; lpSubBlock
0x180018032  mov     rcx, rbx; pBlock
0x180018035  call    cs:__imp_VerQueryValueW
0x18001803b  test    eax, eax
0x18001803d  jnz     short loc_180018041
0x18001803f  jmp     short loc_18001809A
0x180018041  mov     eax, [rsp+4A8h+var_470]
0x180018045  inc     eax
0x180018047  cmp     eax, r13d
0x18001804a  cmova   eax, r13d
0x18001804e  mov     r9d, eax; MaxCount
0x180018051  mov     r8, [rsp+4A8h+Source]; Source
0x180018056  mov     edx, 100h; SizeInWords
0x18001805b  lea     rcx, [rsp+4A8h+Destination]; Destination
0x180018060  call    cs:__imp_wcsncpy_s
0x180018066  mov     [rsp+4A8h+var_23A], di
0x18001806e  lea     rcx, [rsp+4A8h+Destination]; String
0x180018073  call    cs:__imp__wcsupr
0x180018079  lea     rdx, aMicrosoft; "MICROSOFT"
0x180018080  lea     rcx, [rsp+4A8h+Destination]; Str
0x180018085  call    cs:__imp_wcsstr
0x18001808b  test    rax, rax
0x18001808e  jz      short loc_18001809A
0x180018090  mov     [rsp+4A8h+var_478], 1
0x180018098  jmp     short loc_1800180A5
0x18001809a  inc     esi
0x18001809c  mov     [rsp+4A8h+var_46C], esi
0x1800180a0  jmp     loc_180017FE2
0x1800180a5  jmp     short loc_1800180B6
0x1800180a7  mov     rbx, [rsp+4A8h+var_450]
0x1800180ac  mov     r14, [rsp+4A8h+var_448]
0x1800180b1  mov     r15, [rsp+4A8h+var_440]
0x1800180b6  test    rbx, rbx
0x1800180b9  jz      short loc_1800180CF
0x1800180bb  call    cs:__imp_GetProcessHeap
0x1800180c1  mov     rcx, rax; hHeap
0x1800180c4  mov     r8, rbx; lpMem
0x1800180c7  xor     edx, edx; dwFlags
0x1800180c9  call    cs:__imp_HeapFree
0x1800180cf  test    r15, r15
0x1800180d2  jz      short loc_1800180DB
0x1800180d4  mov     eax, [rsp+4A8h+var_478]
0x1800180d8  mov     [r15], eax
0x1800180db  mov     r8d, [rsp+4A8h+var_478]; int
0x1800180e0  mov     rdx, r14; unsigned __int16 *
0x1800180e3  call    ?_Add@CIsMicrosoftDllCache@@AEAAJPEBGH@Z; CIsMicrosoftDllCache::_Add(ushort const *,int)
0x1800180e8  xor     eax, eax
0x1800180ea  mov     rcx, [rsp+4A8h+var_38]
0x1800180f2  xor     rcx, rsp; StackCookie
0x1800180f5  call    __security_check_cookie
0x1800180fa  mov     rbx, [rsp+4A8h+arg_0]
0x180018102  add     rsp, 480h
0x180018109  pop     r15
0x18001810b  pop     r14
0x18001810d  pop     r13
0x18001810f  pop     rdi
0x180018110  pop     rsi
0x180018111  retn
```
