# FindExactRegisteredPC(ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180012860`
- end: `0x1800129e0`
- name: `?FindExactRegisteredPC@@YAJPEBG0PEAPEAG1@Z`
- size: `384`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001478c`
- `0x180016110`

## callees

- `0x1800039f0`
- `0x18000c63c`
- `0x180012674`
- `0x180012860`
- `0x180012e24`
- `0x1800132fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800128d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800128d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129ab`
- `DMCmnUtils!CopyString` at `0x18001299e`
- `DMCmnUtils!CopyString` at `0x18001299e`

## pseudocode

```c
__int64 __fastcall FindExactRegisteredPC(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  signed int StringValue; // ebx
  LSTATUS v7; // eax
  unsigned __int16 *v8; // rax
  __int64 v9; // rcx
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a3 = 0;
  hKey = 0;
  hMem = 0;
  v11 = 0;
  StringValue = CombineCTAndAppId(a1, a2, (unsigned __int16 **)&hMem);
  if ( StringValue >= 0 )
  {
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\PushRouter\\Registrations\\ByCTAndAppId",
           0,
           0xF003Fu,
           &hKey);
    StringValue = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        StringValue = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      StringValue = QueryStringValue(hKey, (const unsigned __int16 *)hMem, 0, a3);
      if ( StringValue >= 0 )
      {
        if ( *a3 )
        {
          StringValue = GetUniqueQueueId(*a3, &v11);
          if ( StringValue >= 0 )
          {
            StringValue = StringCchPrintfW(v14, 0x104u, L"%d", v11);
            if ( StringValue >= 0 )
            {
              v8 = v14;
              v9 = 0x7FFFFFFF;
              do
              {
                if ( !*v8 )
                  break;
                ++v8;
                --v9;
              }
              while ( v9 );
              StringValue = v9 == 0 ? 0x80070057 : 0;
              if ( v9 )
                StringValue = CopyString(v14, v9 != 0 ? 0x7FFFFFFF - v9 : 0, a4);
            }
          }
        }
      }
    }
  }
  LocalFree(hMem);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180012860  push    rbp
0x180012862  push    rbx
0x180012863  push    rsi
0x180012864  push    rdi
0x180012865  push    r14
0x180012867  lea     rbp, [rsp-170h]
0x18001286f  sub     rsp, 270h
0x180012876  mov     rax, cs:__security_cookie
0x18001287d  xor     rax, rsp
0x180012880  mov     [rbp+190h+var_30], rax
0x180012887  xor     r14d, r14d
0x18001288a  mov     rdi, r8
0x18001288d  mov     [r8], r14
0x180012890  mov     rsi, r9
0x180012893  lea     r8, [rsp+290h+hMem]; unsigned __int16 **
0x180012898  mov     [rsp+290h+hKey], r14
0x18001289d  mov     [rsp+290h+hMem], r14
0x1800128a2  mov     [rsp+290h+var_260], r14d
0x1800128a7  call    ?CombineCTAndAppId@@YAJPEBG0PEAPEAG@Z; CombineCTAndAppId(ushort const *,ushort const *,ushort * *)
0x1800128ac  mov     ebx, eax
0x1800128ae  test    eax, eax
0x1800128b0  js      loc_1800129A6
0x1800128b6  lea     rax, [rsp+290h+hKey]
0x1800128bb  mov     r9d, 0F003Fh; samDesired
0x1800128c1  xor     r8d, r8d; ulOptions
0x1800128c4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800128c9  lea     rdx, ?c_szAppRegistrationByCTAndAppId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x1800128d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800128d7  call    cs:__imp_RegOpenKeyExW
0x1800128dd  mov     ebx, eax
0x1800128df  test    eax, eax
0x1800128e1  jz      short loc_1800128F7
0x1800128e3  jle     loc_1800129A6
0x1800128e9  movzx   ebx, ax
0x1800128ec  or      ebx, 80070000h
0x1800128f2  jmp     loc_1800129A6
0x1800128f7  mov     rdx, [rsp+290h+hMem]; unsigned __int16 *
0x1800128fc  mov     r9, rdi; unsigned __int16 **
0x1800128ff  mov     rcx, [rsp+290h+hKey]; HKEY
0x180012904  xor     r8d, r8d; unsigned __int16 *
0x180012907  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18001290c  mov     ebx, eax
0x18001290e  test    eax, eax
0x180012910  js      loc_1800129A6
0x180012916  mov     rcx, [rdi]; unsigned __int16 *
0x180012919  test    rcx, rcx
0x18001291c  jz      loc_1800129A6
0x180012922  lea     rdx, [rsp+290h+var_260]; unsigned int *
0x180012927  call    ?GetUniqueQueueId@@YAJPEBGPEAK@Z; GetUniqueQueueId(ushort const *,ulong *)
0x18001292c  mov     ebx, eax
0x18001292e  test    eax, eax
0x180012930  js      short loc_1800129A6
0x180012932  mov     r9d, [rsp+290h+var_260]
0x180012937  lea     r8, aD; "%d"
0x18001293e  mov     edx, 104h; unsigned __int64
0x180012943  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x180012948  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001294d  mov     ebx, eax
0x18001294f  test    eax, eax
0x180012951  js      short loc_1800129A6
0x180012953  mov     edx, 7FFFFFFFh
0x180012958  lea     rax, [rsp+290h+var_240]
0x18001295d  mov     ecx, edx
0x18001295f  cmp     [rax], r14w
0x180012963  jz      short loc_18001296F
0x180012965  add     rax, 2
0x180012969  sub     rcx, 1
0x18001296d  jnz     short loc_18001295F
0x18001296f  mov     rax, rcx
0x180012972  neg     rax
0x180012975  mov     rax, rcx
0x180012978  sbb     ebx, ebx
0x18001297a  sub     rdx, rcx
0x18001297d  not     ebx
0x18001297f  and     ebx, 80070057h
0x180012985  neg     rax
0x180012988  sbb     r8, r8
0x18001298b  and     r8, rdx
0x18001298e  test    rcx, rcx
0x180012991  jz      short loc_1800129A6
0x180012993  mov     edx, r8d
0x180012996  lea     rcx, [rsp+290h+var_240]
0x18001299b  mov     r8, rsi
0x18001299e  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800129a4  mov     ebx, eax
0x1800129a6  mov     rcx, [rsp+290h+hMem]; hMem
0x1800129ab  call    cs:__imp_LocalFree
0x1800129b1  mov     rcx, [rsp+290h+hKey]; hKey
0x1800129b6  test    rcx, rcx
0x1800129b9  jz      short loc_1800129C1
0x1800129bb  call    cs:__imp_RegCloseKey
0x1800129c1  mov     eax, ebx
0x1800129c3  mov     rcx, [rbp+190h+var_30]
0x1800129ca  xor     rcx, rsp; StackCookie
0x1800129cd  call    __security_check_cookie
0x1800129d2  add     rsp, 270h
0x1800129d9  pop     r14
0x1800129db  pop     rdi
0x1800129dc  pop     rsi
0x1800129dd  pop     rbx
0x1800129de  pop     rbp
0x1800129df  retn
```
