# CLocalConfigProvider::SetValue(uint,CConfigValue const *)

- ea: `0x1800e8ed0`
- end: `0x1800e90cc`
- name: `?SetValue@CLocalConfigProvider@@UEAAJIPEBVCConfigValue@@@Z`
- size: `508`
- prototype: `int(CLocalConfigProvider *__hidden this, unsigned int, const struct CConfigValue *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800a2894`

## callees

- `0x180008b1c`
- `0x18000933c`
- `0x18001d21c`
- `0x18001d324`
- `0x18001dfc4`
- `0x1800a4e18`
- `0x1800a4e74`
- `0x1800a4ed4`
- `0x1800e8ed0`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e8f2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e8f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e90a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e90a4`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800e9073`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueA` at `0x1800e9073`

## string_xrefs

- `0x1800e9058`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\LocalConfigProvider.cpp`
- `0x1800e908a`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\LocalConfigProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocalConfigProvider::SetValue(CLocalConfigProvider *this, int a2, const struct CConfigValue *a3)
{
  const char *v5; // rdi
  RTL_SRWLOCK *v6; // rbp
  const char *v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // eax
  unsigned int v15[4]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( *((_DWORD *)this + 2) == 7 )
    v5 = (const char *)qword_180124FD0[10 * a2 + 1];
  else
    v5 = (const char *)qword_180124FD0[10 * a2];
  *(_QWORD *)&v15[2] = 1;
  v6 = (RTL_SRWLOCK *)((char *)this + 128);
  *(_QWORD *)v15 = (char *)this + 128;
  AcquireSRWLockShared((PSRWLOCK)this + 16);
  if ( *((_QWORD *)this + 17) )
  {
    if ( a3 )
    {
      switch ( *((_BYTE *)a3 + 32) < 8u ? *((char *)a3 + 32) : 0 )
      {
        case 2:
        case 3:
          v15[0] = 0;
          v11 = CConvert::FromVariantNoThrow<unsigned int,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
                  (unsigned __int8 *)a3,
                  (int *)v15);
          v8 = v11;
          if ( v11 < 0 )
          {
            v10 = 70;
            goto LABEL_26;
          }
          v11 = RegSetDwordValue(*((HKEY *)this + 17), 0, v5, v15[0]);
          v8 = v11;
          if ( v11 < 0 )
          {
            v10 = 71;
            goto LABEL_26;
          }
          break;
        case 4:
        case 5:
          *(_QWORD *)v15 = 0;
          v11 = CConvert::FromVariantNoThrow<unsigned __int64,std::monostate,bool,int,unsigned int,__int64,unsigned __int64,double,std::string>(
                  (double *)a3,
                  (double *)v15);
          v8 = v11;
          if ( v11 < 0 )
          {
            v10 = 79;
            goto LABEL_26;
          }
          v11 = RegSetQwordValue(*((HKEY *)this + 17), v12, v5, *(unsigned __int64 *)v15);
          v8 = v11;
          if ( v11 < 0 )
          {
            v10 = 80;
            goto LABEL_26;
          }
          break;
        case 7:
          if ( *((_BYTE *)a3 + 32) != 7 )
            std::_Throw_bad_variant_access();
          if ( *((_QWORD *)a3 + 3) > 0xFu )
            a3 = *(const struct CConfigValue **)a3;
          v11 = RegSetStringValue(*((HKEY *)this + 17), v7, v5, (const char *)a3);
          v8 = v11;
          if ( v11 < 0 )
          {
            v10 = 85;
LABEL_26:
            v9 = (unsigned int)v11;
            goto LABEL_27;
          }
          break;
        default:
          v8 = -2147023092;
          v9 = 2147944204LL;
          v10 = 90;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\LocalConfigProvider.cpp",
            (const char *)v9,
            v15[0]);
          goto LABEL_32;
      }
    }
    else
    {
      v13 = RegDeleteKeyValueA(*((HKEY *)this + 17), 0, v5);
      if ( v13 != 2 && v13 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x62,
               (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\LocalConfigProvider.cpp",
               (const char *)v13,
               v15[0]);
        goto LABEL_32;
      }
    }
    v8 = 0;
    goto LABEL_32;
  }
  v8 = -2147024890;
LABEL_32:
  ReleaseSRWLockShared(v6);
  return v8;
}

```

## disassembly

```asm
0x1800e8ed0  mov     [rsp+arg_18], rbx
0x1800e8ed5  push    rbp
0x1800e8ed6  push    rsi
0x1800e8ed7  push    rdi
0x1800e8ed8  sub     rsp, 40h
0x1800e8edc  mov     rax, cs:__security_cookie
0x1800e8ee3  xor     rax, rsp
0x1800e8ee6  mov     [rsp+58h+var_28], rax
0x1800e8eeb  mov     rbx, r8
0x1800e8eee  mov     rsi, rcx
0x1800e8ef1  movsxd  rax, edx
0x1800e8ef4  lea     rdi, [rax+rax*4]
0x1800e8ef8  add     rdi, rdi
0x1800e8efb  lea     rax, qword_180124FD0
0x1800e8f02  cmp     dword ptr [rcx+8], 7
0x1800e8f06  jnz     short loc_1800E8F0F
0x1800e8f08  mov     rdi, [rax+rdi*8+8]
0x1800e8f0d  jmp     short loc_1800E8F13
0x1800e8f0f  mov     rdi, [rax+rdi*8]
0x1800e8f13  xorps   xmm0, xmm0
0x1800e8f16  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x1800e8f1b  lea     rbp, [rcx+80h]
0x1800e8f22  mov     qword ptr [rsp+58h+var_38], rbp; unsigned int
0x1800e8f27  mov     byte ptr [rsp+58h+var_38+8], 1
0x1800e8f2c  mov     rcx, rbp; SRWLock
0x1800e8f2f  call    cs:__imp_AcquireSRWLockShared
0x1800e8f35  nop
0x1800e8f36  mov     r10, [rsi+88h]
0x1800e8f3d  test    r10, r10
0x1800e8f40  jnz     short loc_1800E8F4C
0x1800e8f42  mov     ebx, 80070006h
0x1800e8f47  jmp     loc_1800E90A1
0x1800e8f4c  test    rbx, rbx
0x1800e8f4f  jz      loc_1800E906B
0x1800e8f55  movsx   eax, byte ptr [rbx+20h]
0x1800e8f59  cmp     byte ptr [rbx+20h], 8
0x1800e8f5d  sbb     ecx, ecx
0x1800e8f5f  and     ecx, eax
0x1800e8f61  sub     ecx, 2
0x1800e8f64  jz      loc_1800E9012
0x1800e8f6a  sub     ecx, 1
0x1800e8f6d  jz      loc_1800E9012
0x1800e8f73  sub     ecx, 1
0x1800e8f76  jz      short loc_1800E8FCA
0x1800e8f78  sub     ecx, 1
0x1800e8f7b  jz      short loc_1800E8FCA
0x1800e8f7d  cmp     ecx, 2
0x1800e8f80  jz      short loc_1800E8F94
0x1800e8f82  mov     ebx, 8007070Ch
0x1800e8f87  mov     r9d, ebx
0x1800e8f8a  mov     edx, 5Ah ; 'Z'
0x1800e8f8f  jmp     loc_1800E9058
0x1800e8f94  cmp     byte ptr [rbx+20h], 7
0x1800e8f98  jnz     loc_1800E90C6
0x1800e8f9e  cmp     qword ptr [rbx+18h], 0Fh
0x1800e8fa3  jbe     short loc_1800E8FA8
0x1800e8fa5  mov     rbx, [rbx]
0x1800e8fa8  mov     r9, rbx; char *
0x1800e8fab  mov     r8, rdi; char *
0x1800e8fae  mov     rcx, r10; HKEY
0x1800e8fb1  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEBD11@Z; RegSetStringValue(HKEY__ *,char const *,char const *,char const *)
0x1800e8fb6  mov     ebx, eax
0x1800e8fb8  test    eax, eax
0x1800e8fba  jns     loc_1800E909F
0x1800e8fc0  mov     edx, 55h ; 'U'
0x1800e8fc5  jmp     loc_1800E9055
0x1800e8fca  mov     qword ptr [rsp+58h+var_38], 0
0x1800e8fd3  lea     rdx, [rsp+58h+var_38]
0x1800e8fd8  mov     rcx, rbx
0x1800e8fdb  call    ??$FromVariantNoThrow@_KUmonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@CConvert@@SAJAEBV?$variant@Umonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@std@@AEA_K@Z; CConvert::FromVariantNoThrow<unsigned __int64,std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string>(std::variant<std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string> const &,unsigned __int64 &)
0x1800e8fe0  mov     ebx, eax
0x1800e8fe2  test    eax, eax
0x1800e8fe4  jns     short loc_1800E8FED
0x1800e8fe6  mov     edx, 4Fh ; 'O'
0x1800e8feb  jmp     short loc_1800E9055
0x1800e8fed  mov     r9, qword ptr [rsp+58h+var_38]; unsigned __int64
0x1800e8ff2  mov     r8, rdi; char *
0x1800e8ff5  mov     rcx, [rsi+88h]; HKEY
0x1800e8ffc  call    ?RegSetQwordValue@@YAJPEAUHKEY__@@PEBD1_K@Z; RegSetQwordValue(HKEY__ *,char const *,char const *,unsigned __int64)
0x1800e9001  mov     ebx, eax
0x1800e9003  test    eax, eax
0x1800e9005  jns     loc_1800E909F
0x1800e900b  mov     edx, 50h ; 'P'
0x1800e9010  jmp     short loc_1800E9055
0x1800e9012  mov     [rsp+58h+var_38], 0; int
0x1800e901a  lea     rdx, [rsp+58h+var_38]
0x1800e901f  mov     rcx, rbx
0x1800e9022  call    ??$FromVariantNoThrow@IUmonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@CConvert@@SAJAEBV?$variant@Umonostate@std@@_NHI_J_KNV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@std@@AEAI@Z; CConvert::FromVariantNoThrow<uint,std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string>(std::variant<std::monostate,bool,int,uint,__int64,unsigned __int64,double,std::string> const &,uint &)
0x1800e9027  mov     ebx, eax
0x1800e9029  test    eax, eax
0x1800e902b  jns     short loc_1800E9034
0x1800e902d  mov     edx, 46h ; 'F'
0x1800e9032  jmp     short loc_1800E9055
0x1800e9034  mov     r9d, [rsp+58h+var_38]; unsigned int
0x1800e9039  mov     r8, rdi; char *
0x1800e903c  xor     edx, edx; char *
0x1800e903e  mov     rcx, [rsi+88h]; HKEY
0x1800e9045  call    ?RegSetDwordValue@@YAJPEAUHKEY__@@PEBD1I@Z; RegSetDwordValue(HKEY__ *,char const *,char const *,uint)
0x1800e904a  mov     ebx, eax
0x1800e904c  test    eax, eax
0x1800e904e  jns     short loc_1800E909F
0x1800e9050  mov     edx, 47h ; 'G'; void *
0x1800e9055  mov     r9d, eax; char *
0x1800e9058  lea     r8, aCW1SSrcDeliver_7; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800e905f  mov     rcx, [rsp+58h]; this
0x1800e9064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9069  jmp     short loc_1800E90A1
0x1800e906b  mov     r8, rdi; lpValueName
0x1800e906e  xor     edx, edx; lpSubKey
0x1800e9070  mov     rcx, r10; hKey
0x1800e9073  call    cs:__imp_RegDeleteKeyValueA
0x1800e9079  cmp     eax, 2
0x1800e907c  jz      short loc_1800E909F
0x1800e907e  test    eax, eax
0x1800e9080  jz      short loc_1800E909F
0x1800e9082  mov     rcx, [rsp+58h]; this
0x1800e9087  mov     r9d, eax; char *
0x1800e908a  lea     r8, aCW1SSrcDeliver_7; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800e9091  mov     edx, 62h ; 'b'; void *
0x1800e9096  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e909b  mov     ebx, eax
0x1800e909d  jmp     short loc_1800E90A1
0x1800e909f  xor     ebx, ebx
0x1800e90a1  mov     rcx, rbp; SRWLock
0x1800e90a4  call    cs:__imp_ReleaseSRWLockShared
0x1800e90aa  mov     eax, ebx
0x1800e90ac  mov     rcx, [rsp+58h+var_28]
0x1800e90b1  xor     rcx, rsp; StackCookie
0x1800e90b4  call    __security_check_cookie
0x1800e90b9  mov     rbx, [rsp+58h+arg_18]
0x1800e90be  add     rsp, 40h
0x1800e90c2  pop     rdi
0x1800e90c3  pop     rsi
0x1800e90c4  pop     rbp
0x1800e90c5  retn
0x1800e90c6  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
```
