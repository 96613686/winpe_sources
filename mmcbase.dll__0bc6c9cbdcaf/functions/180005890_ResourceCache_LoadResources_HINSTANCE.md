# ResourceCache::LoadResources(HINSTANCE__ *)

- ea: `0x180005890`
- end: `0x180005c24`
- name: `?LoadResources@ResourceCache@@SAJPEAUHINSTANCE__@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(HINSTANCE hModule)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001f90`

## callees

- `0x180005890`
- `0x180008630`
- `0x18000b838`
- `0x18000b95c`
- `0x18000b980`
- `0x18000b9cc`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005b0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005b0e`
- `USER32!LoadIconW` at `0x180005a07`
- `USER32!LoadIconW` at `0x180005a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005b5b`

## pseudocode

```c
__int64 __fastcall ResourceCache::LoadResources(HINSTANCE hModule, __int64 a2, WCHAR *a3)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct ResourceCache::_resourceDefinition near **v8; // rdi
  unsigned __int64 v9; // r12
  int v10; // edx
  int v11; // edx
  HICON IconW; // rax
  int Error; // eax
  unsigned int v14; // edx
  int v15; // eax
  UINT v17; // edx
  int StringW; // eax
  unsigned __int64 v19; // r14
  struct ResourceCache::_resourceDefinition *v20; // rax
  struct ResourceCache::_resourceDefinition *v21; // rdx
  __int64 v22; // rcx
  struct ResourceCache::_resourceDefinition *v23; // rcx
  void *v24; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Buffer[512]; // [rsp+40h] [rbp-438h] BYREF

  if ( _InterlockedIncrement(&dword_18002C2F0) != 1 )
  {
    v4 = -2147024726;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v6 = 11;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids, (unsigned int)v4);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( hModule )
  {
    if ( ResourceCache::s_hResourceInstance )
    {
      v4 = -2147023649;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v6 = 13;
        goto LABEL_5;
      }
      goto LABEL_32;
    }
    v7 = WPP_GLOBAL_Control;
    v8 = &ResourceCache::s_resourceDefs;
    v4 = 0;
    v9 = 0;
    while ( 1 )
    {
      v10 = *(_DWORD *)v8;
      v24 = 0;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
          {
            v4 = -2147024809;
            if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 2u )
            {
              WPP_SF_ddd(
                *(_QWORD *)(v7 + 16),
                18,
                WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
                *(unsigned int *)v8,
                *((_DWORD *)v8 + 1),
                -2147024809);
              goto LABEL_21;
            }
            goto LABEL_60;
          }
          IconW = LoadIconW(hModule, (LPCWSTR)*((unsigned __int16 *)v8 + 2));
          v8[2] = (struct ResourceCache::_resourceDefinition near *)IconW;
          if ( IconW )
            goto LABEL_58;
          Error = ResourceCache::LastError();
          v4 = Error;
          v7 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            WPP_SF_dd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              17,
              WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
              *((unsigned int *)v8 + 1),
              Error);
            goto LABEL_58;
          }
        }
        else
        {
          v14 = *((_DWORD *)v8 + 1);
          v8[2] = 0;
          v15 = ResourceCache::InternalLoadResource(hModule, v14, a3, &v24);
          v7 = WPP_GLOBAL_Control;
          v4 = v15;
          if ( v15 >= 0 )
          {
            v8[2] = (struct ResourceCache::_resourceDefinition near *)v24;
            goto LABEL_29;
          }
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            WPP_SF_dd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              16,
              WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
              *((unsigned int *)v8 + 1),
              v15);
            goto LABEL_21;
          }
        }
      }
      else
      {
        v17 = *((_DWORD *)v8 + 1);
        v8[2] = 0;
        StringW = LoadStringW(hModule, v17, Buffer, 512);
        if ( StringW )
        {
          v19 = StringW + 1LL;
          v20 = (struct ResourceCache::_resourceDefinition *)CoTaskMemAlloc(2 * v19);
          v21 = v20;
          if ( !v20 )
          {
            v4 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                15,
                WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
                *((unsigned int *)v8 + 1),
                -2147024882);
LABEL_21:
              v7 = WPP_GLOBAL_Control;
            }
LABEL_60:
            *((_BYTE *)v8 + 9) = 0;
            if ( *((_BYTE *)v8 + 8) )
              goto LABEL_32;
            v4 = 1;
            goto LABEL_30;
          }
          if ( v19 )
          {
            if ( v19 <= 0x7FFFFFFF )
            {
              v22 = 2147483646;
              a3 = Buffer;
              do
              {
                if ( !v22 )
                  break;
                if ( !*a3 )
                  break;
                *(_WORD *)v20 = *a3++;
                v20 = (struct ResourceCache::_resourceDefinition *)((char *)v20 + 2);
                --v22;
                --v19;
              }
              while ( v19 );
              v23 = (struct ResourceCache::_resourceDefinition *)((char *)v20 - 2);
              if ( v19 )
                v23 = v20;
              *(_WORD *)v23 = 0;
            }
            else
            {
              *(_WORD *)v20 = 0;
            }
          }
          v8[2] = v21;
          goto LABEL_58;
        }
        v4 = ResourceCache::LastError();
        if ( v4 >= 0 )
          v4 = -2147418113;
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          WPP_SF_dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
            *((unsigned int *)v8 + 1),
            v4);
LABEL_58:
          v7 = WPP_GLOBAL_Control;
        }
      }
      if ( v4 < 0 )
        goto LABEL_60;
LABEL_29:
      *((_BYTE *)v8 + 9) = 1;
LABEL_30:
      ++v9;
      v8 += 3;
      if ( v9 >= 7 )
      {
        ResourceCache::s_hResourceInstance = hModule;
        goto LABEL_32;
      }
    }
  }
  v4 = -2147024809;
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v6 = 12;
    goto LABEL_5;
  }
LABEL_32:
  _InterlockedDecrement(&dword_18002C2F0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005890  mov     [rsp+arg_8], rbx
0x180005895  mov     [rsp+arg_10], rbp
0x18000589a  push    rsi
0x18000589b  push    rdi
0x18000589c  push    r12
0x18000589e  push    r13
0x1800058a0  push    r14
0x1800058a2  sub     rsp, 450h
0x1800058a9  mov     rax, cs:__security_cookie
0x1800058b0  xor     rax, rsp
0x1800058b3  mov     [rsp+478h+var_38], rax
0x1800058bb  mov     rbp, rcx
0x1800058be  mov     eax, 1
0x1800058c3  lock xadd cs:dword_18002C2F0, eax
0x1800058cb  inc     eax
0x1800058cd  cmp     eax, 1
0x1800058d0  jz      short loc_180005915
0x1800058d2  mov     ebx, 800700AAh
0x1800058d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058de  lea     rsi, WPP_GLOBAL_Control
0x1800058e5  cmp     rcx, rsi
0x1800058e8  jz      loc_180005AA3
0x1800058ee  cmp     byte ptr [rcx+19h], 2
0x1800058f2  jb      loc_180005AA3
0x1800058f8  mov     edx, 0Bh
0x1800058fd  mov     rcx, [rcx+10h]
0x180005901  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x180005908  mov     r9d, ebx
0x18000590b  call    WPP_SF_d
0x180005910  jmp     loc_180005AA3
0x180005915  xor     r13d, r13d
0x180005918  test    rbp, rbp
0x18000591b  jnz     short loc_180005948
0x18000591d  mov     ebx, 80070057h
0x180005922  mov     rcx, cs:WPP_GLOBAL_Control
0x180005929  lea     rsi, WPP_GLOBAL_Control
0x180005930  cmp     rcx, rsi
0x180005933  jz      loc_180005AA3
0x180005939  cmp     byte ptr [rcx+19h], 2
0x18000593d  jb      loc_180005AA3
0x180005943  lea     edx, [rbp+0Ch]
0x180005946  jmp     short loc_1800058FD
0x180005948  cmp     cs:?s_hResourceInstance@ResourceCache@@0PEAUHINSTANCE__@@EA, r13; HINSTANCE__ * ResourceCache::s_hResourceInstance
0x18000594f  jz      short loc_180005981
0x180005951  mov     ebx, 800704DFh
0x180005956  mov     rcx, cs:WPP_GLOBAL_Control
0x18000595d  lea     rsi, WPP_GLOBAL_Control
0x180005964  cmp     rcx, rsi
0x180005967  jz      loc_180005AA3
0x18000596d  cmp     byte ptr [rcx+19h], 2
0x180005971  jb      loc_180005AA3
0x180005977  mov     edx, 0Dh
0x18000597c  jmp     loc_1800058FD
0x180005981  mov     rcx, cs:WPP_GLOBAL_Control
0x180005988  lea     rdi, ?s_resourceDefs@ResourceCache@@0PAU_resourceDefinition@1@A; ResourceCache::_resourceDefinition near * ResourceCache::s_resourceDefs
0x18000598f  mov     ebx, r13d
0x180005992  lea     rsi, WPP_GLOBAL_Control
0x180005999  mov     r12, r13
0x18000599c  mov     edx, [rdi]
0x18000599e  mov     [rsp+478h+var_448], r13
0x1800059a3  test    edx, edx
0x1800059a5  jz      loc_180005AF9
0x1800059ab  sub     edx, 1
0x1800059ae  jz      loc_180005A5D
0x1800059b4  cmp     edx, 1
0x1800059b7  jz      short loc_180005A00
0x1800059b9  mov     ebx, 80070057h
0x1800059be  cmp     rcx, rsi
0x1800059c1  jz      loc_180005C0C
0x1800059c7  cmp     byte ptr [rcx+19h], 2
0x1800059cb  jb      loc_180005C0C
0x1800059d1  mov     eax, [rdi+4]
0x1800059d4  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x1800059db  mov     r9d, [rdi]
0x1800059de  mov     edx, 12h
0x1800059e3  mov     rcx, [rcx+10h]
0x1800059e7  mov     [rsp+478h+var_450], ebx
0x1800059eb  mov     [rsp+478h+var_458], eax
0x1800059ef  call    WPP_SF_ddd
0x1800059f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059fb  jmp     loc_180005C0C
0x180005a00  movzx   edx, word ptr [rdi+4]; lpIconName
0x180005a04  mov     rcx, rbp; hInstance
0x180005a07  call    cs:__imp_LoadIconW
0x180005a0d  mov     [rdi+10h], rax
0x180005a11  test    rax, rax
0x180005a14  jnz     loc_180005BFD
0x180005a1a  call    ?LastError@ResourceCache@@CAJXZ; ResourceCache::LastError(void)
0x180005a1f  mov     ebx, eax
0x180005a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a28  cmp     rcx, rsi
0x180005a2b  jz      loc_180005C04
0x180005a31  cmp     byte ptr [rcx+19h], 2
0x180005a35  jb      loc_180005C04
0x180005a3b  mov     edx, 11h
0x180005a40  mov     [rsp+478h+var_458], eax
0x180005a44  mov     r9d, [rdi+4]
0x180005a48  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x180005a4f  mov     rcx, [rcx+10h]
0x180005a53  call    WPP_SF_dd
0x180005a58  jmp     loc_180005BFD
0x180005a5d  mov     edx, [rdi+4]; unsigned int
0x180005a60  lea     r9, [rsp+478h+var_448]; void **
0x180005a65  mov     rcx, rbp; hModule
0x180005a68  mov     [rdi+10h], r13
0x180005a6c  call    ?InternalLoadResource@ResourceCache@@CAJPEAUHINSTANCE__@@IPEBGAEAPEAX@Z; ResourceCache::InternalLoadResource(HINSTANCE__ *,uint,ushort const *,void * &)
0x180005a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a78  mov     ebx, eax
0x180005a7a  test    eax, eax
0x180005a7c  js      short loc_180005AD8
0x180005a7e  mov     rax, [rsp+478h+var_448]
0x180005a83  mov     [rdi+10h], rax
0x180005a87  mov     byte ptr [rdi+9], 1
0x180005a8b  inc     r12
0x180005a8e  add     rdi, 18h
0x180005a92  cmp     r12, 7
0x180005a96  jb      loc_18000599C
0x180005a9c  mov     cs:?s_hResourceInstance@ResourceCache@@0PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * ResourceCache::s_hResourceInstance
0x180005aa3  lock dec cs:dword_18002C2F0
0x180005aaa  mov     eax, ebx
0x180005aac  mov     rcx, [rsp+478h+var_38]
0x180005ab4  xor     rcx, rsp; StackCookie
0x180005ab7  call    __security_check_cookie
0x180005abc  lea     r11, [rsp+478h+var_28]
0x180005ac4  mov     rbx, [r11+38h]
0x180005ac8  mov     rbp, [r11+40h]
0x180005acc  mov     rsp, r11
0x180005acf  pop     r14
0x180005ad1  pop     r13
0x180005ad3  pop     r12
0x180005ad5  pop     rdi
0x180005ad6  pop     rsi
0x180005ad7  retn
0x180005ad8  cmp     rcx, rsi
0x180005adb  jz      loc_180005C04
0x180005ae1  cmp     byte ptr [rcx+19h], 2
0x180005ae5  jb      loc_180005C04
0x180005aeb  mov     edx, 10h
0x180005af0  mov     [rsp+478h+var_458], eax
0x180005af4  jmp     loc_180005B8F
0x180005af9  mov     edx, [rdi+4]; uID
0x180005afc  lea     r8, [rsp+478h+Buffer]; lpBuffer
0x180005b01  mov     r9d, 200h; cchBufferMax
0x180005b07  mov     [rdi+10h], r13
0x180005b0b  mov     rcx, rbp; hInstance
0x180005b0e  call    cs:__imp_LoadStringW
0x180005b14  test    eax, eax
0x180005b16  jnz     short loc_180005B51
0x180005b18  call    ?LastError@ResourceCache@@CAJXZ; ResourceCache::LastError(void)
0x180005b1d  mov     ebx, eax
0x180005b1f  mov     eax, 8000FFFFh
0x180005b24  test    ebx, ebx
0x180005b26  cmovns  ebx, eax
0x180005b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b30  cmp     rcx, rsi
0x180005b33  jz      loc_180005C04
0x180005b39  cmp     byte ptr [rcx+19h], 2
0x180005b3d  jb      loc_180005C04
0x180005b43  mov     edx, 0Eh
0x180005b48  mov     [rsp+478h+var_458], ebx
0x180005b4c  jmp     loc_180005A44
0x180005b51  movsxd  r14, eax
0x180005b54  inc     r14
0x180005b57  lea     rcx, [r14+r14]; cb
0x180005b5b  call    cs:__imp_CoTaskMemAlloc
0x180005b61  mov     rdx, rax
0x180005b64  test    rax, rax
0x180005b67  jnz     short loc_180005BA8
0x180005b69  mov     ebx, 8007000Eh
0x180005b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b75  cmp     rcx, rsi
0x180005b78  jz      loc_180005C0C
0x180005b7e  cmp     byte ptr [rcx+19h], 2
0x180005b82  jb      loc_180005C0C
0x180005b88  lea     edx, [rax+0Fh]
0x180005b8b  mov     [rsp+478h+var_458], ebx
0x180005b8f  mov     r9d, [rdi+4]
0x180005b93  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x180005b9a  mov     rcx, [rcx+10h]
0x180005b9e  call    WPP_SF_dd
0x180005ba3  jmp     loc_1800059F4
0x180005ba8  test    r14, r14
0x180005bab  jz      short loc_180005BF9
0x180005bad  cmp     r14, 7FFFFFFFh
0x180005bb4  jbe     short loc_180005BBC
0x180005bb6  mov     [rax], r13w
0x180005bba  jmp     short loc_180005BF9
0x180005bbc  mov     ecx, 7FFFFFFEh
0x180005bc1  lea     r8, [rsp+478h+Buffer]
0x180005bc6  test    rcx, rcx
0x180005bc9  jz      short loc_180005BEA
0x180005bcb  movzx   r9d, word ptr [r8]
0x180005bcf  test    r9w, r9w
0x180005bd3  jz      short loc_180005BEA
0x180005bd5  mov     [rax], r9w
0x180005bd9  add     r8, 2
0x180005bdd  add     rax, 2
0x180005be1  dec     rcx
0x180005be4  sub     r14, 1
0x180005be8  jnz     short loc_180005BC6
0x180005bea  test    r14, r14
0x180005bed  lea     rcx, [rax-2]
0x180005bf1  cmovnz  rcx, rax
0x180005bf5  mov     [rcx], r13w
0x180005bf9  mov     [rdi+10h], rdx
0x180005bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c04  test    ebx, ebx
0x180005c06  jns     loc_180005A87
0x180005c0c  mov     [rdi+9], r13b
0x180005c10  cmp     [rdi+8], r13b
0x180005c14  jnz     loc_180005AA3
0x180005c1a  mov     ebx, 1
0x180005c1f  jmp     loc_180005A8B
```
