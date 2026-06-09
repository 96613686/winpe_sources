# CMimeHandler::DoVerb(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *)

- ea: `0x18000fcb0`
- end: `0x18000ff34`
- name: `?DoVerb@CMimeHandler@@UEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(CMimeHandler *this, __int64, struct tagMSG *, struct IOleClientSite *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000eb00`
- `0x18000fcb0`
- `0x18012a020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000fe9f`
- `KERNEL32!GetProcAddress` at `0x18000fe9f`
- `KERNEL32!GetLastError` at `0x18000feaa`
- `KERNEL32!GetLastError` at `0x18000feaa`
- `KERNEL32!Sleep` at `0x18000fe4a`
- `KERNEL32!Sleep` at `0x18000fee0`
- `KERNEL32!Sleep` at `0x18000fe4a`
- `KERNEL32!Sleep` at `0x18000fee0`
- `urlmon!CoInternetCreateSecurityManager` at `0x18000fcf1`
- `urlmon!CoInternetCreateSecurityManager` at `0x18000fcf1`

## pseudocode

```c
__int64 __fastcall CMimeHandler::DoVerb(CMimeHandler *this, __int64 a2, struct tagMSG *a3, struct IOleClientSite *a4)
{
  __int64 **v5; // rsi
  HRESULT SecurityManager; // eax
  signed int v7; // ebx
  __int64 *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // ebp
  __int64 v23; // r14
  HMODULE v24; // rcx
  signed int Module; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  unsigned int v29; // [rsp+50h] [rbp-38h] BYREF
  _DWORD v30[3]; // [rsp+54h] [rbp-34h] BYREF
  int v31; // [rsp+90h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 97) || *((_BYTE *)this + 96) )
  {
    *((_DWORD *)this + 8) = 0;
    return 0;
  }
  v5 = (__int64 **)((char *)this + 104);
  if ( *((_QWORD *)this + 13)
    || (SecurityManager = CoInternetCreateSecurityManager(0, (IInternetSecurityManager **)this + 13, 0),
        *((_DWORD *)this + 8) = SecurityManager,
        v7 = SecurityManager,
        SecurityManager >= 0) )
  {
    v8 = *v5;
    v9 = *((unsigned int *)this + 12);
    v10 = *((_QWORD *)this + 5);
    v30[0] = 0;
    v31 = 0;
    v11 = *v8;
    *(_WORD *)(v10 + 2 * v9) = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _DWORD *, int, _QWORD, _DWORD, int, _DWORD))(v11 + 56))(
            v8,
            *((_QWORD *)this + 5),
            8196,
            v30,
            4,
            0,
            0,
            1,
            0);
    *((_DWORD *)this + 8) = v12;
    v7 = v12;
    if ( v12 >= 0 )
    {
      v13 = *v5;
      v14 = *((unsigned int *)this + 12);
      v15 = *((_QWORD *)this + 5);
      v29 = 0;
      v16 = *v13;
      *(_WORD *)(v15 + 2 * v14) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, unsigned int *, int, _QWORD, _DWORD, int, _DWORD))(v16 + 56))(
              v13,
              *((_QWORD *)this + 5),
              8193,
              &v29,
              4,
              0,
              0,
              1,
              0);
      *((_DWORD *)this + 8) = v17;
      v7 = v17;
      if ( v17 >= 0 )
      {
        v18 = *v5;
        v19 = **v5;
        *(_WORD *)(*((_QWORD *)this + 5) + 2LL * *((unsigned int *)this + 12)) = 0;
        v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, int *, int, _QWORD, _DWORD, int, _DWORD))(v19 + 56))(
                v18,
                *((_QWORD *)this + 5),
                6147,
                &v31,
                4,
                0,
                0,
                1,
                0);
        *((_DWORD *)this + 8) = v20;
        v7 = v20;
        if ( v20 >= 0 )
        {
          if ( v31 )
          {
            v7 = -2147467231;
            *((_DWORD *)this + 8) = -2147467231;
            return (unsigned int)v7;
          }
          v21 = v29;
          v22 = v30[0];
          *(_WORD *)(*((_QWORD *)this + 5) + 2LL * *((unsigned int *)this + 12)) = 0;
          v23 = *((_QWORD *)this + 5);
          while ( _InterlockedExchange(&CDll<&unsigned short near * wDfDll>::_lock, 1) )
            Sleep(0x64u);
          v24 = CDll<&unsigned short near * wDfDll>::_hModule;
          if ( !CDll<&unsigned short near * wDfDll>::_hModule )
          {
            Module = CDll<&unsigned short near * wDfDll>::LoadModule();
            v7 = Module;
            if ( Module < 0 )
            {
              CDll<&unsigned short near * wDfDll>::_lock = 0;
              *((_DWORD *)this + 8) = Module;
              return (unsigned int)v7;
            }
            v24 = CDll<&unsigned short near * wDfDll>::_hModule;
          }
          ++CDll<&unsigned short near * wDfDll>::_lRefCount;
          CDll<&unsigned short near * wDfDll>::_lock = 0;
          ProcAddress = GetProcAddress(v24, "ActivateDeploymentExW");
          if ( ProcAddress )
          {
            v7 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(v23, v22, v21);
          }
          else
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( v7 >= 0 )
              v7 = -2147024883;
          }
          while ( _InterlockedExchange(&CDll<&unsigned short near * wDfDll>::_lock, 1) )
            Sleep(0x64u);
          --CDll<&unsigned short near * wDfDll>::_lRefCount;
          CDll<&unsigned short near * wDfDll>::_lock = 0;
          *((_DWORD *)this + 8) = v7;
          if ( v7 >= 0 )
          {
            *((_BYTE *)this + 96) = 1;
            *((_DWORD *)this + 8) = 0;
            return 0;
          }
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fcb0  mov     [rsp+arg_8], rbx
0x18000fcb5  mov     [rsp+arg_10], rbp
0x18000fcba  push    rsi
0x18000fcbb  push    rdi
0x18000fcbc  push    r12
0x18000fcbe  push    r14
0x18000fcc0  push    r15
0x18000fcc2  sub     rsp, 60h
0x18000fcc6  xor     r15d, r15d
0x18000fcc9  mov     rdi, rcx
0x18000fccc  cmp     [rcx+61h], r15b
0x18000fcd0  jz      loc_18000FF12
0x18000fcd6  cmp     [rcx+60h], r15b
0x18000fcda  jnz     loc_18000FF12
0x18000fce0  lea     rsi, [rcx+68h]
0x18000fce4  cmp     [rsi], r15
0x18000fce7  jnz     short loc_18000FD04
0x18000fce9  xor     r8d, r8d; dwReserved
0x18000fcec  mov     rdx, rsi; ppSM
0x18000fcef  xor     ecx, ecx; pSP
0x18000fcf1  call    cs:__imp_CoInternetCreateSecurityManager
0x18000fcf7  mov     [rdi+20h], eax
0x18000fcfa  mov     ebx, eax
0x18000fcfc  test    eax, eax
0x18000fcfe  js      loc_18000FF19
0x18000fd04  mov     rcx, [rsi]
0x18000fd07  lea     r9, [rsp+88h+var_34]
0x18000fd0c  mov     r8d, [rdi+30h]
0x18000fd10  mov     r12d, 1
0x18000fd16  mov     rdx, [rdi+28h]
0x18000fd1a  mov     [rsp+88h+var_48], r15d
0x18000fd1f  mov     [rsp+88h+var_34], r15d
0x18000fd24  mov     [rsp+88h+arg_0], r15d
0x18000fd2c  lea     ebp, [r12+3]
0x18000fd31  mov     rax, [rcx]
0x18000fd34  mov     [rsp+88h+var_50], r12d
0x18000fd39  mov     [rdx+r8*2], r15w
0x18000fd3e  mov     r8d, 2004h
0x18000fd44  mov     rdx, [rdi+28h]
0x18000fd48  mov     rax, [rax+38h]
0x18000fd4c  mov     [rsp+88h+var_58], r15d
0x18000fd51  mov     [rsp+88h+var_60], r15
0x18000fd56  mov     [rsp+88h+var_68], ebp
0x18000fd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd5f  mov     [rdi+20h], eax
0x18000fd62  mov     ebx, eax
0x18000fd64  test    eax, eax
0x18000fd66  js      loc_18000FF19
0x18000fd6c  mov     rcx, [rsi]
0x18000fd6f  lea     r9, [rsp+88h+var_38]
0x18000fd74  mov     r8d, [rdi+30h]
0x18000fd78  mov     rdx, [rdi+28h]
0x18000fd7c  mov     [rsp+88h+var_48], r15d
0x18000fd81  mov     [rsp+88h+var_38], r15d
0x18000fd86  mov     rax, [rcx]
0x18000fd89  mov     [rsp+88h+var_50], r12d
0x18000fd8e  mov     [rdx+r8*2], r15w
0x18000fd93  mov     r8d, 2001h
0x18000fd99  mov     rdx, [rdi+28h]
0x18000fd9d  mov     rax, [rax+38h]
0x18000fda1  mov     [rsp+88h+var_58], r15d
0x18000fda6  mov     [rsp+88h+var_60], r15
0x18000fdab  mov     [rsp+88h+var_68], ebp
0x18000fdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb4  mov     [rdi+20h], eax
0x18000fdb7  mov     ebx, eax
0x18000fdb9  test    eax, eax
0x18000fdbb  js      loc_18000FF19
0x18000fdc1  mov     rcx, [rsi]
0x18000fdc4  lea     r9, [rsp+88h+arg_0]
0x18000fdcc  mov     r8d, [rdi+30h]
0x18000fdd0  mov     rdx, [rdi+28h]
0x18000fdd4  mov     [rsp+88h+var_48], r15d
0x18000fdd9  mov     rax, [rcx]
0x18000fddc  mov     [rsp+88h+var_50], r12d
0x18000fde1  mov     [rdx+r8*2], r15w
0x18000fde6  mov     r8d, 1803h
0x18000fdec  mov     rdx, [rdi+28h]
0x18000fdf0  mov     rax, [rax+38h]
0x18000fdf4  mov     [rsp+88h+var_58], r15d
0x18000fdf9  mov     [rsp+88h+var_60], r15
0x18000fdfe  mov     [rsp+88h+var_68], ebp
0x18000fe02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe07  mov     [rdi+20h], eax
0x18000fe0a  mov     ebx, eax
0x18000fe0c  test    eax, eax
0x18000fe0e  js      loc_18000FF19
0x18000fe14  cmp     [rsp+88h+arg_0], r15d
0x18000fe1c  jz      short loc_18000FE2B
0x18000fe1e  mov     ebx, 80004021h
0x18000fe23  mov     [rdi+20h], ebx
0x18000fe26  jmp     loc_18000FF19
0x18000fe2b  mov     edx, [rdi+30h]
0x18000fe2e  mov     rcx, [rdi+28h]
0x18000fe32  mov     esi, [rsp+88h+var_38]
0x18000fe36  mov     ebp, [rsp+88h+var_34]
0x18000fe3a  mov     [rcx+rdx*2], r15w
0x18000fe3f  mov     r14, [rdi+28h]
0x18000fe43  jmp     short loc_18000FE50
0x18000fe45  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000fe4a  call    cs:__imp_Sleep
0x18000fe50  mov     eax, r12d
0x18000fe53  xchg    eax, cs:?_lock@?$CDll@$1?wDfDll@@3PAGA@@1JA; long CDll<&ushort near * wDfDll>::_lock
0x18000fe59  test    eax, eax
0x18000fe5b  jnz     short loc_18000FE45
0x18000fe5d  mov     rcx, cs:?_hModule@?$CDll@$1?wDfDll@@3PAGA@@1PEAUHINSTANCE__@@EA; HINSTANCE__ * CDll<&ushort near * wDfDll>::_hModule
0x18000fe64  test    rcx, rcx
0x18000fe67  jnz     short loc_18000FE8A
0x18000fe69  call    ?LoadModule@?$CDll@$1?wDfDll@@3PAGA@@KAJXZ; CDll<&ushort near * wDfDll>::LoadModule(void)
0x18000fe6e  mov     ebx, eax
0x18000fe70  test    eax, eax
0x18000fe72  jns     short loc_18000FE83
0x18000fe74  mov     cs:?_lock@?$CDll@$1?wDfDll@@3PAGA@@1JA, r15d; long CDll<&ushort near * wDfDll>::_lock
0x18000fe7b  mov     [rdi+20h], eax
0x18000fe7e  jmp     loc_18000FF19
0x18000fe83  mov     rcx, cs:?_hModule@?$CDll@$1?wDfDll@@3PAGA@@1PEAUHINSTANCE__@@EA; hModule
0x18000fe8a  add     cs:?_lRefCount@?$CDll@$1?wDfDll@@3PAGA@@1JA, r12d; long CDll<&ushort near * wDfDll>::_lRefCount
0x18000fe91  lea     rdx, aActivatedeploy_0; "ActivateDeploymentExW"
0x18000fe98  mov     cs:?_lock@?$CDll@$1?wDfDll@@3PAGA@@1JA, r15d; long CDll<&ushort near * wDfDll>::_lock
0x18000fe9f  call    cs:__imp_GetProcAddress
0x18000fea5  test    rax, rax
0x18000fea8  jnz     short loc_18000FECA
0x18000feaa  call    cs:__imp_GetLastError
0x18000feb0  mov     ebx, eax
0x18000feb2  test    eax, eax
0x18000feb4  jle     short loc_18000FEBF
0x18000feb6  movzx   ebx, ax
0x18000feb9  or      ebx, 80070000h
0x18000febf  test    ebx, ebx
0x18000fec1  js      short loc_18000FEE6
0x18000fec3  mov     ebx, 8007000Dh
0x18000fec8  jmp     short loc_18000FEE6
0x18000feca  mov     r8d, esi
0x18000fecd  mov     edx, ebp
0x18000fecf  mov     rcx, r14
0x18000fed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fed7  mov     ebx, eax
0x18000fed9  jmp     short loc_18000FEE6
0x18000fedb  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000fee0  call    cs:__imp_Sleep
0x18000fee6  mov     eax, r12d
0x18000fee9  xchg    eax, cs:?_lock@?$CDll@$1?wDfDll@@3PAGA@@1JA; long CDll<&ushort near * wDfDll>::_lock
0x18000feef  test    eax, eax
0x18000fef1  jnz     short loc_18000FEDB
0x18000fef3  sub     cs:?_lRefCount@?$CDll@$1?wDfDll@@3PAGA@@1JA, r12d; long CDll<&ushort near * wDfDll>::_lRefCount
0x18000fefa  mov     cs:?_lock@?$CDll@$1?wDfDll@@3PAGA@@1JA, r15d; long CDll<&ushort near * wDfDll>::_lock
0x18000ff01  mov     [rdi+20h], ebx
0x18000ff04  test    ebx, ebx
0x18000ff06  js      short loc_18000FF19
0x18000ff08  mov     [rdi+60h], r12b
0x18000ff0c  mov     [rdi+20h], r15d
0x18000ff10  jmp     short loc_18000FF16
0x18000ff12  mov     [rcx+20h], r15d
0x18000ff16  mov     ebx, r15d
0x18000ff19  lea     r11, [rsp+88h+var_28]
0x18000ff1e  mov     eax, ebx
0x18000ff20  mov     rbx, [r11+38h]
0x18000ff24  mov     rbp, [r11+40h]
0x18000ff28  mov     rsp, r11
0x18000ff2b  pop     r15
0x18000ff2d  pop     r14
0x18000ff2f  pop     r12
0x18000ff31  pop     rdi
0x18000ff32  pop     rsi
0x18000ff33  retn
```
