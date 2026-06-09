# _drr_UpdateLocStoreWithRetries

- ea: `0x18000542c`
- end: `0x180005564`
- name: `_drr_UpdateLocStoreWithRetries`
- size: `312`
- prototype: `_BOOL8 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180005c00`
- `0x180006230`

## callees

- `0x1800052f8`
- `0x18000542c`
- `0x18000702c`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005533`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000547e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000547e`
- `ntdll!EtwEventWrite` at `0x18000552a`
- `ntdll!EtwEventWrite` at `0x18000552a`

## pseudocode

```c
_BOOL8 __fastcall drr_UpdateLocStoreWithRetries(__int64 a1, __int64 *a2, __int64 *a3)
{
  DWORD v6; // ecx
  unsigned int v7; // ebx
  int v8; // eax
  HLOCAL v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  DWORD updated; // [rsp+20h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-38h]
  _QWORD v15[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-20h]
  int v17; // [rsp+48h] [rbp-18h]
  int v18; // [rsp+4Ch] [rbp-14h]

  updated = drr_UpdateLocStore(a1, a2, a3);
  v6 = updated;
  if ( updated )
  {
    v7 = 0;
    while ( 1 )
    {
      Sleep(*((_DWORD *)qword_18000FC50 + v7));
      updated = drr_UpdateLocStore(a1, a2, a3);
      v6 = updated;
      if ( !updated )
        break;
      if ( ++v7 >= 6 )
      {
        if ( (unsigned int)g_dwLoglevel > 1 )
        {
          hMem = 0;
          v15[0] = &updated;
          v15[1] = 4;
          v8 = LogErrorCodeAndText(updated);
          v9 = hMem;
          if ( v8 && hMem )
          {
            v10 = -1;
            do
              ++v10;
            while ( *((_WORD *)hMem + v10) );
            v16 = (__int64 *)hMem;
            v11 = 2 * v10 + 2;
          }
          else
          {
            v16 = &qword_18000FCA0;
            v11 = 2;
          }
          v17 = v11;
          v18 = 0;
          if ( qword_1800138C8 )
            EtwEventWrite(qword_1800138C8, DRR_LOG_ERROR_LOCSTOREWRITE, 2, v15);
          LocalFree(v9);
          v6 = updated;
        }
        return v6 == 0;
      }
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x18000542c  mov     [rsp-28h+arg_18], rbx
0x180005431  push    rbp
0x180005432  push    rsi
0x180005433  push    rdi
0x180005434  push    r14
0x180005436  push    r15
0x180005438  mov     rbp, rsp
0x18000543b  sub     rsp, 60h
0x18000543f  mov     rax, cs:__security_cookie
0x180005446  xor     rax, rsp
0x180005449  mov     [rbp+var_10], rax
0x18000544d  xor     r15d, r15d
0x180005450  mov     r14, r8
0x180005453  mov     [rbp+var_40], r15d
0x180005457  mov     rsi, rdx
0x18000545a  mov     rdi, rcx
0x18000545d  call    _drr_UpdateLocStore
0x180005462  mov     [rbp+var_40], eax
0x180005465  mov     ecx, eax
0x180005467  test    eax, eax
0x180005469  jz      loc_18000553C
0x18000546f  mov     ebx, r15d
0x180005472  mov     ecx, ebx
0x180005474  lea     rax, qword_18000FC50
0x18000547b  mov     ecx, [rax+rcx*4]; dwMilliseconds
0x18000547e  call    cs:__imp_Sleep
0x180005484  mov     r8, r14
0x180005487  mov     rdx, rsi
0x18000548a  mov     rcx, rdi
0x18000548d  call    _drr_UpdateLocStore
0x180005492  mov     [rbp+var_40], eax
0x180005495  mov     ecx, eax; dwMessageId
0x180005497  test    eax, eax
0x180005499  jz      loc_18000553C
0x18000549f  inc     ebx
0x1800054a1  cmp     ebx, 6
0x1800054a4  jb      short loc_180005472
0x1800054a6  cmp     cs:g_dwLoglevel, 1
0x1800054ad  jbe     loc_18000553C
0x1800054b3  lea     rax, [rbp+var_40]
0x1800054b7  mov     [rbp+hMem], r15
0x1800054bb  lea     rdx, [rbp+hMem]
0x1800054bf  mov     [rbp+var_30], rax
0x1800054c3  mov     [rbp+var_28], 4
0x1800054cb  call    _LogErrorCodeAndText
0x1800054d0  mov     rbx, [rbp+hMem]
0x1800054d4  mov     r8d, 2
0x1800054da  test    eax, eax
0x1800054dc  jz      short loc_1800054FE
0x1800054de  test    rbx, rbx
0x1800054e1  jz      short loc_1800054FE
0x1800054e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800054e7  inc     rax
0x1800054ea  cmp     [rbx+rax*2], r15w
0x1800054ef  jnz     short loc_1800054E7
0x1800054f1  mov     [rbp+var_20], rbx
0x1800054f5  lea     eax, ds:2[rax*2]
0x1800054fc  jmp     short loc_18000550C
0x1800054fe  lea     rax, qword_18000FCA0
0x180005505  mov     [rbp+var_20], rax
0x180005509  mov     eax, r8d
0x18000550c  mov     rcx, cs:qword_1800138C8
0x180005513  mov     [rbp+var_18], eax
0x180005516  mov     [rbp+var_14], r15d
0x18000551a  test    rcx, rcx
0x18000551d  jz      short loc_180005530
0x18000551f  lea     r9, [rbp+var_30]
0x180005523  lea     rdx, DRR_LOG_ERROR_LOCSTOREWRITE
0x18000552a  call    cs:__imp_EtwEventWrite
0x180005530  mov     rcx, rbx; hMem
0x180005533  call    cs:__imp_LocalFree
0x180005539  mov     ecx, [rbp+var_40]
0x18000553c  test    ecx, ecx
0x18000553e  mov     eax, r15d
0x180005541  setz    al
0x180005544  mov     rcx, [rbp+var_10]
0x180005548  xor     rcx, rsp; StackCookie
0x18000554b  call    __security_check_cookie
0x180005550  mov     rbx, [rsp+60h+arg_18]
0x180005558  add     rsp, 60h
0x18000555c  pop     r15
0x18000555e  pop     r14
0x180005560  pop     rdi
0x180005561  pop     rsi
0x180005562  pop     rbp
0x180005563  retn
```
