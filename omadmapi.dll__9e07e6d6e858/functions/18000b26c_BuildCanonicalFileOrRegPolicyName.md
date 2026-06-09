# BuildCanonicalFileOrRegPolicyName

- ea: `0x18000b26c`
- end: `0x18000b4a8`
- name: `BuildCanonicalFileOrRegPolicyName`
- size: `572`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016700`
- `0x180016a10`

## callees

- `0x180009bc0`
- `0x18000b26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x18000b303`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x18000b303`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b32e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b32e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b486`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b486`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3e3`
- `DMCmnUtils!CopyString` at `0x18000b2e4`
- `DMCmnUtils!CopyString` at `0x18000b2e4`
- `iri!__imp_IriCreateFromString` at `0x18000b2b6`
- `iri!__imp_IriCreateFromString` at `0x18000b2b6`
- `iri!__imp_IriClose` at `0x18000b46f`
- `iri!__imp_IriClose` at `0x18000b46f`
- `iri!__imp_IriMutableClose` at `0x18000b458`
- `iri!__imp_IriMutableClose` at `0x18000b458`
- `iri!__imp_IriMakeConstantEx` at `0x18000b37b`
- `iri!__imp_IriMakeConstantEx` at `0x18000b37b`
- `iri!__imp_IriGetAsString` at `0x18000b3c2`
- `iri!__imp_IriGetAsString` at `0x18000b41b`
- `iri!__imp_IriGetAsString` at `0x18000b3c2`
- `iri!__imp_IriGetAsString` at `0x18000b41b`
- `iri!__imp_IriAppendSegment` at `0x18000b355`
- `iri!__imp_IriAppendSegment` at `0x18000b355`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildCanonicalFileOrRegPolicyName(__int64 a1, const unsigned __int16 *a2, _QWORD *a3)
{
  int appended; // ebx
  unsigned __int16 **v6; // rax
  wchar_t *v7; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  unsigned __int64 v10; // rax
  HLOCAL v11; // rax
  void *v12; // rdi
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+30h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v17 = 0;
  v14 = 0;
  v16 = 0;
  Str = 0;
  *a3 = 0;
  appended = IriCreateFromString(a1, 1, &v17);
  if ( appended >= 0 )
  {
    v6 = (unsigned __int16 **)ipx::replace<ipx::detail::_HandleTraits<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>>(&Str);
    appended = CopyString(a2, 0xFFFFFFFF, v6);
    if ( appended >= 0 )
    {
      if ( (unsigned int)_o__wcsupr_s(Str, 0x7FFFFFFF) )
      {
        appended = -2147418113;
      }
      else
      {
        v7 = Str;
        if ( Str )
        {
          while ( 1 )
          {
            v8 = wcschr(v7, 0x5Cu);
            v9 = v8;
            if ( v8 )
            {
              *v8 = 0;
              v9 = v8 + 1;
            }
            appended = IriAppendSegment(v17, v7, 0);
            if ( appended < 0 )
              break;
            v7 = v9;
            if ( !v9 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          appended = IriMakeConstantEx(&v17, &v14);
          if ( appended >= 0 )
          {
            v17 = 0;
            appended = IriGetAsString(v14, 0, 0xFFFFFFFFLL, 5, 0, 0, &v16);
            if ( appended >= 0 )
            {
              v10 = 2LL * v16;
              if ( v10 > 0xFFFFFFFF )
              {
                appended = -2147024362;
              }
              else
              {
                v11 = LocalAlloc(0, (unsigned int)v10);
                v12 = v11;
                if ( v11 )
                {
                  appended = IriGetAsString(v14, 0, 0xFFFFFFFFLL, 5, v11, v16, 0);
                  if ( appended >= 0 )
                    *a3 = v12;
                  else
                    LocalFree(v12);
                }
                else
                {
                  appended = -2147024882;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v17 )
    appended = IriMutableClose();
  if ( v14 )
    appended = IriClose();
  if ( Str )
    LocalFree(Str);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000b26c  mov     [rsp-18h+arg_0], rbx
0x18000b271  mov     [rsp-18h+arg_8], rsi
0x18000b276  push    rbp
0x18000b277  push    rdi
0x18000b278  push    r15
0x18000b27a  mov     rbp, rsp
0x18000b27d  sub     rsp, 50h
0x18000b281  mov     rsi, r8
0x18000b284  mov     rdi, rdx
0x18000b287  mov     [rbp+arg_18], 0
0x18000b28f  mov     [rbp+var_10], 0
0x18000b297  mov     [rbp+arg_10], 0
0x18000b29e  mov     [rbp+Str], 0
0x18000b2a6  mov     qword ptr [r8], 0
0x18000b2ad  lea     r8, [rbp+arg_18]
0x18000b2b1  mov     edx, 1
0x18000b2b6  call    cs:__imp_IriCreateFromString
0x18000b2bd  nop     dword ptr [rax+rax+00h]
0x18000b2c2  mov     ebx, eax
0x18000b2c4  test    eax, eax
0x18000b2c6  js      loc_18000B44F
0x18000b2cc  lea     rcx, [rbp+Str]
0x18000b2d0  call    ??$replace@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAGAEAV?$unique_any@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>> &)
0x18000b2d5  mov     r8, rax
0x18000b2d8  mov     r15d, 0FFFFFFFFh
0x18000b2de  mov     edx, r15d
0x18000b2e1  mov     rcx, rdi
0x18000b2e4  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000b2eb  nop     dword ptr [rax+rax+00h]
0x18000b2f0  mov     ebx, eax
0x18000b2f2  test    eax, eax
0x18000b2f4  js      loc_18000B44F
0x18000b2fa  mov     edx, 7FFFFFFFh
0x18000b2ff  mov     rcx, [rbp+Str]
0x18000b303  call    cs:__imp__o__wcsupr_s
0x18000b30a  nop     dword ptr [rax+rax+00h]
0x18000b30f  test    eax, eax
0x18000b311  jz      short loc_18000B31D
0x18000b313  mov     ebx, 8000FFFFh
0x18000b318  jmp     loc_18000B44F
0x18000b31d  mov     rbx, [rbp+Str]
0x18000b321  test    rbx, rbx
0x18000b324  jz      short loc_18000B373
0x18000b326  mov     edx, 5Ch ; '\'; Ch
0x18000b32b  mov     rcx, rbx; Str
0x18000b32e  call    cs:__imp_wcschr
0x18000b335  nop     dword ptr [rax+rax+00h]
0x18000b33a  mov     rdi, rax
0x18000b33d  test    rax, rax
0x18000b340  jz      short loc_18000B34B
0x18000b342  xor     ecx, ecx
0x18000b344  mov     [rax], cx
0x18000b347  add     rdi, 2
0x18000b34b  xor     r8d, r8d
0x18000b34e  mov     rdx, rbx
0x18000b351  mov     rcx, [rbp+arg_18]
0x18000b355  call    cs:__imp_IriAppendSegment
0x18000b35c  nop     dword ptr [rax+rax+00h]
0x18000b361  mov     ebx, eax
0x18000b363  test    eax, eax
0x18000b365  js      loc_18000B44F
0x18000b36b  mov     rbx, rdi
0x18000b36e  test    rdi, rdi
0x18000b371  jnz     short loc_18000B326
0x18000b373  lea     rdx, [rbp+var_10]
0x18000b377  lea     rcx, [rbp+arg_18]
0x18000b37b  call    cs:__imp_IriMakeConstantEx
0x18000b382  nop     dword ptr [rax+rax+00h]
0x18000b387  mov     ebx, eax
0x18000b389  test    eax, eax
0x18000b38b  js      loc_18000B44F
0x18000b391  mov     [rbp+arg_18], 0
0x18000b399  lea     rax, [rbp+arg_10]
0x18000b39d  mov     [rsp+50h+var_20], rax
0x18000b3a2  mov     [rsp+50h+var_28], 0
0x18000b3aa  mov     [rsp+50h+var_30], 0
0x18000b3b3  mov     r9d, 5
0x18000b3b9  mov     r8d, r15d
0x18000b3bc  xor     edx, edx
0x18000b3be  mov     rcx, [rbp+var_10]
0x18000b3c2  call    cs:__imp_IriGetAsString
0x18000b3c9  nop     dword ptr [rax+rax+00h]
0x18000b3ce  mov     ebx, eax
0x18000b3d0  test    eax, eax
0x18000b3d2  js      short loc_18000B44F
0x18000b3d4  mov     eax, [rbp+arg_10]
0x18000b3d7  add     rax, rax
0x18000b3da  cmp     rax, r15
0x18000b3dd  ja      short loc_18000B44A
0x18000b3df  mov     edx, eax; uBytes
0x18000b3e1  xor     ecx, ecx; uFlags
0x18000b3e3  call    cs:__imp_LocalAlloc
0x18000b3ea  nop     dword ptr [rax+rax+00h]
0x18000b3ef  mov     rdi, rax
0x18000b3f2  test    rax, rax
0x18000b3f5  jz      short loc_18000B443
0x18000b3f7  mov     edx, [rbp+arg_10]
0x18000b3fa  mov     [rsp+50h+var_20], 0
0x18000b403  mov     [rsp+50h+var_28], edx
0x18000b407  mov     [rsp+50h+var_30], rax
0x18000b40c  mov     r9d, 5
0x18000b412  mov     r8d, r15d
0x18000b415  xor     edx, edx
0x18000b417  mov     rcx, [rbp+var_10]
0x18000b41b  call    cs:__imp_IriGetAsString
0x18000b422  nop     dword ptr [rax+rax+00h]
0x18000b427  mov     ebx, eax
0x18000b429  test    eax, eax
0x18000b42b  jns     short loc_18000B43E
0x18000b42d  mov     rcx, rdi; hMem
0x18000b430  call    cs:__imp_LocalFree
0x18000b437  nop     dword ptr [rax+rax+00h]
0x18000b43c  jmp     short loc_18000B44F
0x18000b43e  mov     [rsi], rdi
0x18000b441  jmp     short loc_18000B44F
0x18000b443  mov     ebx, 8007000Eh
0x18000b448  jmp     short loc_18000B44F
0x18000b44a  mov     ebx, 80070216h
0x18000b44f  mov     rcx, [rbp+arg_18]
0x18000b453  test    rcx, rcx
0x18000b456  jz      short loc_18000B466
0x18000b458  call    cs:__imp_IriMutableClose
0x18000b45f  nop     dword ptr [rax+rax+00h]
0x18000b464  mov     ebx, eax
0x18000b466  mov     rcx, [rbp+var_10]
0x18000b46a  test    rcx, rcx
0x18000b46d  jz      short loc_18000B47D
0x18000b46f  call    cs:__imp_IriClose
0x18000b476  nop     dword ptr [rax+rax+00h]
0x18000b47b  mov     ebx, eax
0x18000b47d  mov     rcx, [rbp+Str]; hMem
0x18000b481  test    rcx, rcx
0x18000b484  jz      short loc_18000B492
0x18000b486  call    cs:__imp_LocalFree
0x18000b48d  nop     dword ptr [rax+rax+00h]
0x18000b492  mov     eax, ebx
0x18000b494  mov     rbx, [rsp+50h+arg_0]
0x18000b499  mov     rsi, [rsp+50h+arg_8]
0x18000b49e  add     rsp, 50h
0x18000b4a2  pop     r15
0x18000b4a4  pop     rdi
0x18000b4a5  pop     rbp
0x18000b4a6  retn
```
