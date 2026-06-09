# RasSrvGetDatabaseHandle

- ea: `0x18002049c`
- end: `0x180020622`
- name: `RasSrvGetDatabaseHandle`
- size: `390`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `26`
- callee_count: `9`
- tags: ``

## callers

- `0x180022184`
- `0x18002277c`
- `0x180022850`
- `0x1800229f8`
- `0x180022aec`
- `0x18002326c`
- `0x180023994`
- `0x180023bac`
- `0x180023e5c`
- `0x180024104`
- `0x18002439c`
- `0x180024c4c`
- `0x180024e38`
- `0x180024eec`
- `0x1800250c0`
- `0x180025314`
- `0x1800253ec`
- `0x1800254c4`
- `0x180025730`
- `0x180025878`
- `0x180025b7c`
- `0x180025c0c`
- `0x180025d14`
- `0x180025f54`
- `0x180026010`
- `0x1800262cc`

## callees

- `0x18002049c`
- `0x180021438`
- `0x180027730`
- `0x180028164`
- `0x180028460`
- `0x18002947c`
- `0x18002b970`
- `0x18002c318`
- `0x18002f3b0`

## import_xrefs

- `USER32!GetPropW` at `0x1800204cf`
- `USER32!GetPropW` at `0x1800204cf`
- `USER32!GetParent` at `0x180020522`
- `USER32!GetParent` at `0x180020522`
- `USER32!GetWindowTextW` at `0x180020538`
- `USER32!GetWindowTextW` at `0x180020538`

## pseudocode

```c
__int64 __fastcall RasSrvGetDatabaseHandle(HWND hWnd, int a2, __int64 *a3)
{
  __int64 *v6; // rcx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  __int64 *v11; // rbx
  HWND Parent; // rax
  const wchar_t *StringPcch; // rax
  STRSAFE_LPWSTR *v14; // r9
  __int64 *v15; // rdi
  unsigned int *v16; // rax
  unsigned int *v17; // rbx
  bool v18; // zf
  __int64 v19; // rax
  WCHAR String[64]; // [rsp+30h] [rbp-98h] BYREF

  v6 = (__int64 *)*((_QWORD *)GetPropW(hWnd, lpString) + 1);
  if ( v6 && a3 )
  {
    v7 = a2 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 6;
        if ( !v9 )
        {
          v15 = v6 + 5;
          if ( !v6[5] && v6 != (__int64 *)-40LL )
          {
            v16 = (unsigned int *)RassrvAlloc(24, 1);
            v17 = v16;
            if ( v16 )
            {
              miscReloadDatabase(v16);
              v18 = *v17 == 0;
              v17[3] = 0;
              if ( !v18 )
                v17[3] = 1;
              *v15 = (__int64)v17;
              v17[1] = 0;
            }
          }
          v19 = *v15;
          goto LABEL_24;
        }
        if ( v9 != 8 )
          return 1003;
        v11 = v6 + 4;
        if ( !v6[4] )
        {
          Parent = GetParent(hWnd);
          if ( !GetWindowTextW(Parent, String, 64) )
          {
            StringPcch = (const wchar_t *)PszLoadStringPcch(hInstance);
            StringCchCopyWrapW(String, 0x40u, StringPcch, v14);
          }
          netDbOpen(v11, String);
        }
      }
      else
      {
        v11 = v6 + 3;
        if ( !v6[3] )
          usrOpenLocalDatabase(v6 + 3);
      }
    }
    else
    {
      v11 = v6 + 2;
      if ( !v6[2] )
        devOpenDatabase(v6 + 2);
    }
    v19 = *v11;
LABEL_24:
    *a3 = v19;
    return 0;
  }
  return 87;
}

```

## disassembly

```asm
0x18002049c  mov     [rsp+arg_8], rbx
0x1800204a1  mov     [rsp+arg_18], rsi
0x1800204a6  push    rdi
0x1800204a7  sub     rsp, 0C0h
0x1800204ae  mov     rax, cs:__security_cookie
0x1800204b5  xor     rax, rsp
0x1800204b8  mov     [rsp+0C8h+var_18], rax
0x1800204c0  mov     ebx, edx
0x1800204c2  mov     rsi, r8
0x1800204c5  mov     rdx, cs:lpString; lpString
0x1800204cc  mov     rdi, rcx
0x1800204cf  call    cs:__imp_GetPropW
0x1800204d5  mov     rcx, [rax+8]
0x1800204d9  test    rcx, rcx
0x1800204dc  jz      loc_1800205F8
0x1800204e2  test    rsi, rsi
0x1800204e5  jz      loc_1800205F8
0x1800204eb  sub     ebx, 1
0x1800204ee  jz      loc_1800205DC
0x1800204f4  sub     ebx, 1
0x1800204f7  jz      loc_1800205C8
0x1800204fd  sub     ebx, 6
0x180020500  jz      short loc_18002057A
0x180020502  cmp     ebx, 8
0x180020505  jz      short loc_180020511
0x180020507  mov     eax, 3EBh
0x18002050c  jmp     loc_1800205FD
0x180020511  lea     rbx, [rcx+20h]
0x180020515  cmp     qword ptr [rbx], 0
0x180020519  jnz     loc_1800205EE
0x18002051f  mov     rcx, rdi; hWnd
0x180020522  call    cs:__imp_GetParent
0x180020528  mov     edi, 40h ; '@'
0x18002052d  lea     rdx, [rsp+0C8h+String]; lpString
0x180020532  mov     rcx, rax; hWnd
0x180020535  mov     r8d, edi; nMaxCount
0x180020538  call    cs:__imp_GetWindowTextW
0x18002053e  test    eax, eax
0x180020540  jnz     short loc_18002056B
0x180020542  mov     rcx, cs:hInstance; hModule
0x180020549  lea     r8, [rsp+0C8h+var_A8]
0x18002054e  mov     edx, 1CC7h
0x180020553  mov     [rsp+0C8h+var_A8], eax
0x180020557  call    PszLoadStringPcch
0x18002055c  mov     r8, rax
0x18002055f  lea     rcx, [rsp+0C8h+String]
0x180020564  mov     edx, edi
0x180020566  call    StringCchCopyWrapW
0x18002056b  lea     rdx, [rsp+0C8h+String]
0x180020570  mov     rcx, rbx
0x180020573  call    netDbOpen
0x180020578  jmp     short loc_1800205EE
0x18002057a  lea     rdi, [rcx+28h]
0x18002057e  cmp     qword ptr [rdi], 0
0x180020582  jnz     short loc_1800205C3
0x180020584  test    rdi, rdi
0x180020587  jz      short loc_1800205C3
0x180020589  mov     edx, 1
0x18002058e  lea     ecx, [rdx+17h]
0x180020591  call    RassrvAlloc
0x180020596  mov     rbx, rax
0x180020599  test    rax, rax
0x18002059c  jz      short loc_1800205C3
0x18002059e  mov     rcx, rax
0x1800205a1  call    miscReloadDatabase
0x1800205a6  cmp     dword ptr [rbx], 0
0x1800205a9  mov     dword ptr [rbx+0Ch], 0
0x1800205b0  jz      short loc_1800205B9
0x1800205b2  mov     dword ptr [rbx+0Ch], 1
0x1800205b9  mov     [rdi], rbx
0x1800205bc  mov     dword ptr [rbx+4], 0
0x1800205c3  mov     rax, [rdi]
0x1800205c6  jmp     short loc_1800205F1
0x1800205c8  lea     rbx, [rcx+18h]
0x1800205cc  cmp     qword ptr [rbx], 0
0x1800205d0  jnz     short loc_1800205EE
0x1800205d2  mov     rcx, rbx
0x1800205d5  call    usrOpenLocalDatabase
0x1800205da  jmp     short loc_1800205EE
0x1800205dc  lea     rbx, [rcx+10h]
0x1800205e0  cmp     qword ptr [rbx], 0
0x1800205e4  jnz     short loc_1800205EE
0x1800205e6  mov     rcx, rbx
0x1800205e9  call    devOpenDatabase
0x1800205ee  mov     rax, [rbx]
0x1800205f1  mov     [rsi], rax
0x1800205f4  xor     eax, eax
0x1800205f6  jmp     short loc_1800205FD
0x1800205f8  mov     eax, 57h ; 'W'
0x1800205fd  mov     rcx, [rsp+0C8h+var_18]
0x180020605  xor     rcx, rsp; StackCookie
0x180020608  call    __security_check_cookie
0x18002060d  lea     r11, [rsp+0C8h+var_8]
0x180020615  mov     rbx, [r11+18h]
0x180020619  mov     rsi, [r11+28h]
0x18002061d  mov     rsp, r11
0x180020620  pop     rdi
0x180020621  retn
```
