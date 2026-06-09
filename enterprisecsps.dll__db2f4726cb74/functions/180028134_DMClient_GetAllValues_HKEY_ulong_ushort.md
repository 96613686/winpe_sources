# DMClient::GetAllValues(HKEY__ *,ulong *,ushort * * *)

- ea: `0x180028134`
- end: `0x180028386`
- name: `?GetAllValues@DMClient@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z`
- size: `594`
- prototype: `__int64 __fastcall(HKEY hKey, _DWORD *, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800279ec`
- `0x180027d9c`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x180028134`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800282bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800282bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180028322`
- `OLEAUT32!__imp_SysFreeString` at `0x180028322`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800282aa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800282aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800281b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800281b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800281fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800281fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028258`

## pseudocode

```c
__int64 __fastcall DMClient::GetAllValues(HKEY hKey, _DWORD *a2, unsigned int *a3, unsigned __int16 ***a4)
{
  DWORD v4; // r14d
  LSTATUS v8; // eax
  signed int v9; // ebx
  size_t v10; // rbx
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  WCHAR *v13; // rdi
  __int64 v14; // rcx
  LSTATUS v15; // eax
  BSTR v16; // rax
  DWORD v17; // eax
  OLECHAR *v18; // rcx
  DWORD cb[4]; // [rsp+60h] [rbp-10h] BYREF
  DWORD v21; // [rsp+B0h] [rbp+40h] BYREF
  DWORD v22; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 0;
  v22 = 0;
  v21 = 0;
  cb[0] = 0;
  if ( hKey && a2 && a3 )
  {
    *a2 = 0;
    *(_QWORD *)a3 = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &v22, &v21, 0, 0, 0);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v9 = ULongLongToULong(8LL * v22, cb);
      if ( v9 >= 0 )
      {
        v10 = cb[0];
        v11 = CoTaskMemAlloc(cb[0]);
        v12 = v11;
        if ( v11 )
        {
          v13 = 0;
          memset_0(v11, 0, v10);
          v14 = v21 + 1;
          if ( (unsigned int)v14 < v21 )
          {
            v21 = -1;
            v9 = -2147024362;
          }
          else
          {
            ++v21;
            cb[0] = 0;
            v9 = ULongLongToULong(2 * v14, cb);
            if ( v9 >= 0 )
            {
              v13 = (WCHAR *)CoTaskMemAlloc(cb[0]);
              if ( v13 )
              {
                while ( 1 )
                {
                  if ( v4 >= v22 )
                  {
                    *a2 = v22;
                    *(_QWORD *)a3 = v12;
                    goto LABEL_29;
                  }
                  cb[0] = v21;
                  *v13 = 0;
                  v15 = RegEnumValueW(hKey, v4, v13, cb, 0, 0, 0, 0);
                  if ( v15 )
                    break;
                  v16 = SysAllocString(v13);
                  v12[v4] = v16;
                  if ( !v16 )
                  {
                    v9 = -2147024882;
                    v4 = 0;
                    goto LABEL_24;
                  }
                  ++v4;
                }
                v4 = 0;
                if ( v15 > 0 )
                  v9 = (unsigned __int16)v15 | 0x80070000;
                else
                  v9 = v15;
              }
              else
              {
                v9 = -2147024882;
              }
            }
          }
LABEL_24:
          v17 = v22;
          if ( v22 )
          {
            do
            {
              v18 = (OLECHAR *)v12[v4];
              if ( v18 )
              {
                SysFreeString(v18);
                v12[v4] = 0;
                v17 = v22;
              }
              ++v4;
            }
            while ( v4 < v17 );
          }
          CoTaskMemFree(v12);
          if ( v13 )
LABEL_29:
            CoTaskMemFree(v13);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028134  mov     r11, rsp
0x180028137  mov     [r11+10h], rbx
0x18002813b  push    rbp
0x18002813c  push    rsi
0x18002813d  push    rdi
0x18002813e  push    r12
0x180028140  push    r13
0x180028142  push    r14
0x180028144  push    r15
0x180028146  mov     rbp, rsp
0x180028149  sub     rsp, 70h
0x18002814d  xor     r14d, r14d
0x180028150  mov     r15, r8
0x180028153  mov     [rbp+arg_18], r14d
0x180028157  mov     r12, rdx
0x18002815a  mov     [rbp+arg_0], r14d
0x18002815e  mov     r13, rcx
0x180028161  mov     [rbp+cb], r14d
0x180028165  test    rcx, rcx
0x180028168  jz      loc_180028366
0x18002816e  test    rdx, rdx
0x180028171  jz      loc_180028366
0x180028177  test    r8, r8
0x18002817a  jz      loc_180028366
0x180028180  mov     [r11-50h], r14
0x180028184  lea     rax, [rbp+arg_0]
0x180028188  mov     [r11-58h], r14
0x18002818c  xor     r9d, r9d; lpReserved
0x18002818f  mov     [r11-60h], r14
0x180028193  mov     [r11-68h], rax
0x180028197  lea     rax, [rbp+arg_18]
0x18002819b  mov     [r11-70h], rax
0x18002819f  mov     [rdx], r14d
0x1800281a2  xor     edx, edx; lpClass
0x1800281a4  mov     [r11-78h], r14
0x1800281a8  mov     [r8], r14
0x1800281ab  xor     r8d, r8d; lpcchClass
0x1800281ae  mov     [r11-80h], r14
0x1800281b2  mov     [rsp+70h+lpcSubKeys], r14; lpcSubKeys
0x1800281b7  call    cs:__imp_RegQueryInfoKeyW
0x1800281be  nop     dword ptr [rax+rax+00h]
0x1800281c3  mov     ebx, eax
0x1800281c5  test    eax, eax
0x1800281c7  jz      short loc_1800281DD
0x1800281c9  jle     loc_18002836B
0x1800281cf  movzx   ebx, ax
0x1800281d2  or      ebx, 80070000h
0x1800281d8  jmp     loc_18002836B
0x1800281dd  mov     ecx, [rbp+arg_18]
0x1800281e0  lea     rdx, [rbp+cb]; unsigned int *
0x1800281e4  shl     rcx, 3; unsigned __int64
0x1800281e8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800281ed  mov     ebx, eax
0x1800281ef  test    eax, eax
0x1800281f1  js      loc_18002836B
0x1800281f7  mov     ebx, [rbp+cb]
0x1800281fa  mov     ecx, ebx; cb
0x1800281fc  call    cs:__imp_CoTaskMemAlloc
0x180028203  nop     dword ptr [rax+rax+00h]
0x180028208  mov     rsi, rax
0x18002820b  test    rax, rax
0x18002820e  jnz     short loc_18002821A
0x180028210  mov     ebx, 8007000Eh
0x180028215  jmp     loc_18002836B
0x18002821a  mov     r8, rbx; Size
0x18002821d  xor     edx, edx; Val
0x18002821f  mov     rcx, rsi; void *
0x180028222  mov     rdi, r14
0x180028225  call    memset_0
0x18002822a  mov     eax, [rbp+arg_0]
0x18002822d  lea     ecx, [rax+1]
0x180028230  cmp     ecx, eax
0x180028232  jb      loc_180028303
0x180028238  mov     [rbp+arg_0], ecx
0x18002823b  lea     rdx, [rbp+cb]; unsigned int *
0x18002823f  add     rcx, rcx; unsigned __int64
0x180028242  mov     [rbp+cb], r14d
0x180028246  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002824b  mov     ebx, eax
0x18002824d  test    eax, eax
0x18002824f  js      loc_18002830F
0x180028255  mov     ecx, [rbp+cb]; cb
0x180028258  call    cs:__imp_CoTaskMemAlloc
0x18002825f  nop     dword ptr [rax+rax+00h]
0x180028264  mov     rdi, rax
0x180028267  test    rax, rax
0x18002826a  jnz     short loc_180028276
0x18002826c  mov     ebx, 8007000Eh
0x180028271  jmp     loc_18002830F
0x180028276  mov     eax, [rbp+arg_18]
0x180028279  cmp     r14d, eax
0x18002827c  jnb     short loc_1800282FA
0x18002827e  mov     eax, [rbp+arg_0]
0x180028281  lea     r9, [rbp+cb]; lpcchValueName
0x180028285  mov     [rbp+cb], eax
0x180028288  mov     r8, rdi; lpValueName
0x18002828b  xor     eax, eax
0x18002828d  mov     edx, r14d; dwIndex
0x180028290  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180028295  mov     rcx, r13; hKey
0x180028298  mov     [rsp+70h+lpData], rax; lpData
0x18002829d  mov     [rsp+70h+lpType], rax; lpType
0x1800282a2  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x1800282a7  mov     [rdi], ax
0x1800282aa  call    cs:__imp_RegEnumValueW
0x1800282b1  nop     dword ptr [rax+rax+00h]
0x1800282b6  test    eax, eax
0x1800282b8  jnz     short loc_1800282E4
0x1800282ba  mov     rcx, rdi; psz
0x1800282bd  call    cs:__imp_SysAllocString
0x1800282c4  nop     dword ptr [rax+rax+00h]
0x1800282c9  mov     ecx, r14d
0x1800282cc  mov     [rsi+rcx*8], rax
0x1800282d0  test    rax, rax
0x1800282d3  jz      short loc_1800282DA
0x1800282d5  inc     r14d
0x1800282d8  jmp     short loc_180028276
0x1800282da  mov     ebx, 8007000Eh
0x1800282df  xor     r14d, r14d
0x1800282e2  jmp     short loc_18002830F
0x1800282e4  xor     r14d, r14d
0x1800282e7  test    eax, eax
0x1800282e9  jg      short loc_1800282EF
0x1800282eb  mov     ebx, eax
0x1800282ed  jmp     short loc_18002830F
0x1800282ef  movzx   ebx, ax
0x1800282f2  or      ebx, 80070000h
0x1800282f8  jmp     short loc_18002830F
0x1800282fa  mov     [r12], eax
0x1800282fe  mov     [r15], rsi
0x180028301  jmp     short loc_180028355
0x180028303  mov     [rbp+arg_0], 0FFFFFFFFh
0x18002830a  mov     ebx, 80070216h
0x18002830f  mov     eax, [rbp+arg_18]
0x180028312  test    eax, eax
0x180028314  jz      short loc_180028341
0x180028316  mov     r15d, r14d
0x180028319  mov     rcx, [rsi+r15*8]; bstrString
0x18002831d  test    rcx, rcx
0x180028320  jz      short loc_180028339
0x180028322  call    cs:__imp_SysFreeString
0x180028329  nop     dword ptr [rax+rax+00h]
0x18002832e  mov     qword ptr [rsi+r15*8], 0
0x180028336  mov     eax, [rbp+arg_18]
0x180028339  inc     r14d
0x18002833c  cmp     r14d, eax
0x18002833f  jb      short loc_180028316
0x180028341  mov     rcx, rsi; pv
0x180028344  call    cs:__imp_CoTaskMemFree
0x18002834b  nop     dword ptr [rax+rax+00h]
0x180028350  test    rdi, rdi
0x180028353  jz      short loc_18002836B
0x180028355  mov     rcx, rdi; pv
0x180028358  call    cs:__imp_CoTaskMemFree
0x18002835f  nop     dword ptr [rax+rax+00h]
0x180028364  jmp     short loc_18002836B
0x180028366  mov     ebx, 80070057h
0x18002836b  mov     eax, ebx
0x18002836d  mov     rbx, [rsp+70h+arg_8]
0x180028375  add     rsp, 70h
0x180028379  pop     r15
0x18002837b  pop     r14
0x18002837d  pop     r13
0x18002837f  pop     r12
0x180028381  pop     rdi
0x180028382  pop     rsi
0x180028383  pop     rbp
0x180028384  retn
```
