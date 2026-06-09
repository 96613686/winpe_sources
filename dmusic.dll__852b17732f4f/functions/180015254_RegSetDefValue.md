# RegSetDefValue

- ea: `0x180015254`
- end: `0x1800153bf`
- name: `RegSetDefValue`
- size: `363`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, char *, LPCSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015474`

## callees

- `0x1800016d0`
- `0x180015254`
- `0x1800153c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180015386`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180015386`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001532d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001532d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015393`

## pseudocode

```c
LSTATUS __fastcall RegSetDefValue(char *lpSubKey, char *a2, LPCSTR lpValueName, BYTE *lpData)
{
  char *v7; // r9
  __int64 v8; // r10
  __int64 v9; // rax
  char *v10; // rax
  LSTATUS result; // eax
  BYTE *v12; // rax
  __int64 v13; // rcx
  LSTATUS v14; // ebx
  HKEY hKey; // [rsp+50h] [rbp-448h] BYREF
  char v16[1024]; // [rsp+60h] [rbp-438h] BYREF

  hKey = 0;
  if ( a2 )
  {
    v7 = v16;
    v8 = 1024;
    v9 = 2147483646;
    do
    {
      if ( !v9 )
        break;
      if ( !*lpSubKey )
        break;
      *v7++ = *lpSubKey++;
      --v9;
      --v8;
    }
    while ( v8 );
    v10 = v7 - 1;
    if ( v8 )
      v10 = v7;
    *v10 = 0;
    StringCchCatA(v16, 0x400u, "\\");
    StringCchCatA(v16, 0x400u, a2);
    lpSubKey = v16;
  }
  result = RegCreateKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !result )
  {
    if ( !lpData )
      return 14;
    v12 = lpData;
    v13 = 0x7FFFFFFF;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    if ( v13 )
    {
      v14 = RegSetValueExA(hKey, lpValueName, 0, 1u, lpData, v13 != 0 ? 0x7FFFFFFF - v13 + 1 : 1);
      RegCloseKey(hKey);
      return v14;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015254  push    rbx
0x180015256  push    rsi
0x180015257  push    rdi
0x180015258  push    r14
0x18001525a  sub     rsp, 478h
0x180015261  mov     rax, cs:__security_cookie
0x180015268  xor     rax, rsp
0x18001526b  mov     [rsp+498h+var_38], rax
0x180015273  mov     [rsp+498h+hKey], 0
0x18001527c  mov     rbx, r9
0x18001527f  mov     rsi, r8
0x180015282  mov     rdi, rdx
0x180015285  test    rdx, rdx
0x180015288  jz      short loc_1800152F1
0x18001528a  mov     r14d, 400h
0x180015290  lea     r9, [rsp+498h+var_438]
0x180015295  mov     r10d, r14d
0x180015298  mov     eax, 7FFFFFFEh
0x18001529d  test    rax, rax
0x1800152a0  jz      short loc_1800152BA
0x1800152a2  mov     dl, [rcx]
0x1800152a4  test    dl, dl
0x1800152a6  jz      short loc_1800152BA
0x1800152a8  mov     [r9], dl
0x1800152ab  inc     rcx
0x1800152ae  inc     r9
0x1800152b1  dec     rax
0x1800152b4  sub     r10, 1
0x1800152b8  jnz     short loc_18001529D
0x1800152ba  test    r10, r10
0x1800152bd  lea     rax, [r9-1]
0x1800152c1  lea     r8, asc_180025938; "\\"
0x1800152c8  mov     rdx, r14; unsigned __int64
0x1800152cb  cmovnz  rax, r9
0x1800152cf  lea     rcx, [rsp+498h+var_438]; char *
0x1800152d4  mov     byte ptr [rax], 0
0x1800152d7  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800152dc  mov     r8, rdi; char *
0x1800152df  lea     rcx, [rsp+498h+var_438]; char *
0x1800152e4  mov     rdx, r14; unsigned __int64
0x1800152e7  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800152ec  lea     rcx, [rsp+498h+var_438]
0x1800152f1  mov     [rsp+498h+lpdwDisposition], 0; lpdwDisposition
0x1800152fa  lea     rax, [rsp+498h+hKey]
0x1800152ff  mov     [rsp+498h+phkResult], rax; phkResult
0x180015304  mov     rdx, rcx; lpSubKey
0x180015307  mov     [rsp+498h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180015310  xor     r9d, r9d; lpClass
0x180015313  mov     [rsp+498h+samDesired], 0F003Fh; samDesired
0x18001531b  xor     r8d, r8d; Reserved
0x18001531e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180015325  mov     [rsp+498h+dwOptions], 0; dwOptions
0x18001532d  call    cs:__imp_RegCreateKeyExA
0x180015333  test    eax, eax
0x180015335  jnz     short loc_1800153A2
0x180015337  test    rbx, rbx
0x18001533a  jz      short loc_18001539D
0x18001533c  mov     r8d, 7FFFFFFFh
0x180015342  mov     rax, rbx
0x180015345  mov     ecx, r8d
0x180015348  cmp     byte ptr [rax], 0
0x18001534b  jz      short loc_180015356
0x18001534d  inc     rax
0x180015350  sub     rcx, 1
0x180015354  jnz     short loc_180015348
0x180015356  sub     r8, rcx
0x180015359  mov     rax, rcx
0x18001535c  neg     rax
0x18001535f  sbb     rax, rax
0x180015362  and     rax, r8
0x180015365  test    rcx, rcx
0x180015368  jz      short loc_18001539D
0x18001536a  mov     rcx, [rsp+498h+hKey]; hKey
0x18001536f  inc     eax
0x180015371  mov     [rsp+498h+samDesired], eax; cbData
0x180015375  mov     r9d, 1; dwType
0x18001537b  xor     r8d, r8d; Reserved
0x18001537e  mov     qword ptr [rsp+498h+dwOptions], rbx; lpData
0x180015383  mov     rdx, rsi; lpValueName
0x180015386  call    cs:__imp_RegSetValueExA
0x18001538c  mov     rcx, [rsp+498h+hKey]; hKey
0x180015391  mov     ebx, eax
0x180015393  call    cs:__imp_RegCloseKey
0x180015399  mov     eax, ebx
0x18001539b  jmp     short loc_1800153A2
0x18001539d  mov     eax, 0Eh
0x1800153a2  mov     rcx, [rsp+498h+var_38]
0x1800153aa  xor     rcx, rsp; StackCookie
0x1800153ad  call    __security_check_cookie
0x1800153b2  add     rsp, 478h
0x1800153b9  pop     r14
0x1800153bb  pop     rdi
0x1800153bc  pop     rsi
0x1800153bd  pop     rbx
0x1800153be  retn
```
