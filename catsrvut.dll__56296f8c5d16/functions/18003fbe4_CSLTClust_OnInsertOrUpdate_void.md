# CSLTClust::OnInsertOrUpdate(void)

- ea: `0x18003fbe4`
- end: `0x18003fe22`
- name: `?OnInsertOrUpdate@CSLTClust@@AEAAJXZ`
- size: `574`
- prototype: `__int64 __fastcall(CSLTClust *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003fe60`

## callees

- `0x18003fbe4`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003fcab`
- `msvcrt!_wcsicmp` at `0x18003fd3e`
- `msvcrt!_wcsicmp` at `0x18003fdd9`
- `msvcrt!_wcsicmp` at `0x18003fcab`
- `msvcrt!_wcsicmp` at `0x18003fd3e`
- `msvcrt!_wcsicmp` at `0x18003fdd9`
- `KERNEL32!GetComputerNameW` at `0x18003fc95`
- `KERNEL32!GetComputerNameW` at `0x18003fc95`

## pseudocode

```c
__int64 __fastcall CSLTClust::OnInsertOrUpdate(CSLTClust *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  int v8; // eax
  int v9; // [rsp+48h] [rbp+7h] BYREF
  int v10; // [rsp+4Ch] [rbp+Bh] BYREF
  wchar_t *String2; // [rsp+50h] [rbp+Fh] BYREF
  wchar_t *v12; // [rsp+58h] [rbp+17h] BYREF
  DWORD nSize; // [rsp+60h] [rbp+1Fh] BYREF
  __int64 v14; // [rsp+68h] [rbp+27h] BYREF
  WCHAR Buffer[16]; // [rsp+70h] [rbp+2Fh] BYREF

  v14 = 0;
  v2 = *((_QWORD *)this + 6);
  v9 = 0;
  v3 = *((unsigned int *)this + 16);
  v10 = 0;
  String2 = 0;
  v12 = 0;
  nSize = 16;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, _QWORD, wchar_t **))(*(_QWORD *)v2 + 152LL))(
         v2,
         v3,
         &v9,
         0,
         0,
         &String2);
  if ( v4 >= 0 )
  {
    v5 = *(_QWORD *)((char *)this + 68) - TID_COMPUTERLIST;
    if ( !v5 )
      v5 = *(_QWORD *)((char *)this + 76) - 0x291C23C9A0008082LL;
    if ( !v5 )
    {
      if ( !GetComputerNameW(Buffer, &nSize) )
        return 2147549183LL;
      if ( !_wcsicmp(Buffer, String2) )
      {
LABEL_7:
        v4 = -2146368456;
        goto LABEL_25;
      }
      v4 = 1;
    }
    if ( String2 )
    {
      if ( (v9 & 2) != 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
        if ( v4 >= 0 )
        {
          while ( 1 )
          {
            v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 40LL))(*((_QWORD *)this + 6));
            v4 = v6;
            if ( v6 == -2146367487 )
              break;
            if ( v6 < 0 )
              goto LABEL_25;
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, wchar_t **))(**((_QWORD **)this + 6) + 64LL))(
              *((_QWORD *)this + 6),
              *((unsigned int *)this + 16),
              0,
              0,
              &v12);
            if ( !_wcsicmp(String2, v12) )
              goto LABEL_7;
          }
          v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 6) + 88LL))(
                 *((_QWORD *)this + 6),
                 &v14);
          if ( v4 >= 0 )
          {
            while ( 1 )
            {
              v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 6) + 112LL))(
                     *((_QWORD *)this + 6),
                     &v10);
              v4 = v8;
              if ( v8 == -2146367487 )
                break;
              if ( v8 < 0 )
                goto LABEL_25;
              if ( (unsigned int)(v10 - 1) <= 1 )
              {
                v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD, _QWORD, wchar_t **))(**((_QWORD **)this + 6)
                                                                                                  + 152LL))(
                       *((_QWORD *)this + 6),
                       *((unsigned int *)this + 16),
                       &v9,
                       0,
                       0,
                       &v12);
                if ( v4 < 0 )
                  goto LABEL_25;
                if ( !_wcsicmp(String2, v12) )
                  goto LABEL_7;
              }
            }
            v4 = 0;
          }
        }
      }
    }
  }
LABEL_25:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003fbe4  mov     r11, rsp
0x18003fbe7  mov     [r11+10h], rbx
0x18003fbeb  mov     [r11+18h], rdi
0x18003fbef  push    rbp
0x18003fbf0  lea     rbp, [r11-5Fh]
0x18003fbf4  sub     rsp, 90h
0x18003fbfb  mov     rax, cs:__security_cookie
0x18003fc02  xor     rax, rsp
0x18003fc05  mov     [rbp+57h+var_8], rax
0x18003fc09  mov     rdi, rcx
0x18003fc0c  mov     [rbp+57h+var_30], 0
0x18003fc14  mov     rcx, [rcx+30h]
0x18003fc18  lea     rdx, [rbp+57h+String2]
0x18003fc1c  mov     [r11-70h], rdx
0x18003fc20  lea     r8, [rbp+57h+var_50]
0x18003fc24  mov     [rbp+57h+var_50], 0
0x18003fc2b  xor     r9d, r9d
0x18003fc2e  mov     edx, [rdi+40h]
0x18003fc31  mov     [rbp+57h+var_4C], 0
0x18003fc38  mov     [rbp+57h+String2], 0
0x18003fc40  mov     [rbp+57h+var_40], 0
0x18003fc48  mov     [rbp+57h+nSize], 10h
0x18003fc4f  mov     rax, [rcx]
0x18003fc52  mov     qword ptr [r11-78h], 0
0x18003fc5a  mov     rax, [rax+98h]
0x18003fc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc66  mov     ebx, eax
0x18003fc68  test    eax, eax
0x18003fc6a  js      loc_18003FDEA
0x18003fc70  mov     rax, [rdi+44h]
0x18003fc74  sub     rax, cs:TID_COMPUTERLIST
0x18003fc7b  jnz     short loc_18003FC88
0x18003fc7d  mov     rax, [rdi+4Ch]
0x18003fc81  sub     rax, cs:qword_180061280
0x18003fc88  test    rax, rax
0x18003fc8b  jnz     short loc_18003FCC4
0x18003fc8d  lea     rdx, [rbp+57h+nSize]; nSize
0x18003fc91  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18003fc95  call    cs:__imp_GetComputerNameW
0x18003fc9b  test    eax, eax
0x18003fc9d  jz      loc_18003FD4D
0x18003fca3  mov     rdx, [rbp+57h+String2]; String2
0x18003fca7  lea     rcx, [rbp+57h+Buffer]; String1
0x18003fcab  call    cs:__imp__wcsicmp
0x18003fcb1  test    eax, eax
0x18003fcb3  jnz     short loc_18003FCBF
0x18003fcb5  mov     ebx, 80110438h
0x18003fcba  jmp     loc_18003FDEA
0x18003fcbf  mov     ebx, 1
0x18003fcc4  cmp     [rbp+57h+String2], 0
0x18003fcc9  jz      loc_18003FDEA
0x18003fccf  test    byte ptr [rbp+57h+var_50], 2
0x18003fcd3  jz      loc_18003FDEA
0x18003fcd9  mov     rcx, [rdi+30h]
0x18003fcdd  mov     rax, [rcx]
0x18003fce0  mov     rax, [rax+20h]
0x18003fce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fce9  mov     ebx, eax
0x18003fceb  test    eax, eax
0x18003fced  js      loc_18003FDEA
0x18003fcf3  mov     rcx, [rdi+30h]
0x18003fcf7  mov     rax, [rcx]
0x18003fcfa  mov     rax, [rax+28h]
0x18003fcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd03  mov     ebx, eax
0x18003fd05  cmp     eax, 80110801h
0x18003fd0a  jz      short loc_18003FD57
0x18003fd0c  test    eax, eax
0x18003fd0e  js      loc_18003FDEA
0x18003fd14  mov     rcx, [rdi+30h]
0x18003fd18  lea     rdx, [rbp+57h+var_40]
0x18003fd1c  mov     [rsp+90h+var_70], rdx
0x18003fd21  xor     r9d, r9d
0x18003fd24  mov     edx, [rdi+40h]
0x18003fd27  xor     r8d, r8d
0x18003fd2a  mov     rax, [rcx]
0x18003fd2d  mov     rax, [rax+40h]
0x18003fd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd36  mov     rdx, [rbp+57h+var_40]; String2
0x18003fd3a  mov     rcx, [rbp+57h+String2]; String1
0x18003fd3e  call    cs:__imp__wcsicmp
0x18003fd44  test    eax, eax
0x18003fd46  jnz     short loc_18003FCF3
0x18003fd48  jmp     loc_18003FCB5
0x18003fd4d  mov     eax, 8000FFFFh
0x18003fd52  jmp     loc_18003FE01
0x18003fd57  mov     rcx, [rdi+30h]
0x18003fd5b  lea     rdx, [rbp+57h+var_30]
0x18003fd5f  mov     rax, [rcx]
0x18003fd62  mov     rax, [rax+58h]
0x18003fd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd6b  mov     ebx, eax
0x18003fd6d  test    eax, eax
0x18003fd6f  js      short loc_18003FDEA
0x18003fd71  mov     rcx, [rdi+30h]
0x18003fd75  lea     rdx, [rbp+57h+var_4C]
0x18003fd79  mov     rax, [rcx]
0x18003fd7c  mov     rax, [rax+70h]
0x18003fd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd85  mov     ebx, eax
0x18003fd87  cmp     eax, 80110801h
0x18003fd8c  jz      short loc_18003FDE8
0x18003fd8e  test    eax, eax
0x18003fd90  js      short loc_18003FDEA
0x18003fd92  mov     eax, [rbp+57h+var_4C]
0x18003fd95  dec     eax
0x18003fd97  cmp     eax, 1
0x18003fd9a  ja      short loc_18003FD71
0x18003fd9c  mov     rcx, [rdi+30h]
0x18003fda0  lea     rdx, [rbp+57h+var_40]
0x18003fda4  mov     [rsp+90h+var_68], rdx
0x18003fda9  lea     r8, [rbp+57h+var_50]
0x18003fdad  mov     edx, [rdi+40h]
0x18003fdb0  xor     r9d, r9d
0x18003fdb3  mov     [rsp+90h+var_70], 0
0x18003fdbc  mov     rax, [rcx]
0x18003fdbf  mov     rax, [rax+98h]
0x18003fdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdcb  mov     ebx, eax
0x18003fdcd  test    eax, eax
0x18003fdcf  js      short loc_18003FDEA
0x18003fdd1  mov     rdx, [rbp+57h+var_40]; String2
0x18003fdd5  mov     rcx, [rbp+57h+String2]; String1
0x18003fdd9  call    cs:__imp__wcsicmp
0x18003fddf  test    eax, eax
0x18003fde1  jnz     short loc_18003FD71
0x18003fde3  jmp     loc_18003FCB5
0x18003fde8  xor     ebx, ebx
0x18003fdea  mov     rcx, [rbp+57h+var_30]
0x18003fdee  test    rcx, rcx
0x18003fdf1  jz      short loc_18003FDFF
0x18003fdf3  mov     rax, [rcx]
0x18003fdf6  mov     rax, [rax+10h]
0x18003fdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdff  mov     eax, ebx
0x18003fe01  mov     rcx, [rbp+57h+var_8]
0x18003fe05  xor     rcx, rsp; StackCookie
0x18003fe08  call    __security_check_cookie
0x18003fe0d  lea     r11, [rsp+90h+var_s0]
0x18003fe15  mov     rbx, [r11+18h]
0x18003fe19  mov     rdi, [r11+20h]
0x18003fe1d  mov     rsp, r11
0x18003fe20  pop     rbp
0x18003fe21  retn
```
