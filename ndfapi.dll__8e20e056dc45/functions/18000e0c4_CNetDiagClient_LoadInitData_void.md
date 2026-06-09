# CNetDiagClient::LoadInitData(void)

- ea: `0x18000e0c4`
- end: `0x18000e2ce`
- name: `?LoadInitData@CNetDiagClient@@QEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000d390`

## callees

- `0x1800089b4`
- `0x180008a60`
- `0x18000c9b0`
- `0x18000cfa0`
- `0x18000e0c4`
- `0x18001bdc0`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000e19c`
- `ole32!CoTaskMemAlloc` at `0x18000e22a`
- `ole32!CoTaskMemAlloc` at `0x18000e19c`
- `ole32!CoTaskMemAlloc` at `0x18000e22a`
- `ole32!CoTaskMemFree` at `0x18000e274`
- `ole32!CoTaskMemFree` at `0x18000e274`
- `wdi!WdiGetParameterCount` at `0x18000e0fe`
- `wdi!WdiGetParameterCount` at `0x18000e0fe`
- `wdi!WdiGetParameterDataLength` at `0x18000e215`
- `wdi!WdiGetParameterDataLength` at `0x18000e215`
- `wdi!WdiGetParameterData` at `0x18000e24a`
- `wdi!WdiGetParameterData` at `0x18000e24a`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::LoadInitData(CNetDiagClient *this)
{
  struct tagHELPER_ATTRIBUTE *v2; // r14
  unsigned int v3; // r12d
  int v4; // r15d
  int ParameterCount; // edi
  __int64 v6; // rsi
  unsigned int v7; // ebx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  unsigned int v9; // ebx
  void *v10; // r15
  LPVOID v11; // rax
  void *v13; // [rsp+20h] [rbp-28h]
  unsigned int v14; // [rsp+90h] [rbp+48h] BYREF
  SIZE_T cb; // [rsp+98h] [rbp+50h] BYREF
  int v16; // [rsp+A0h] [rbp+58h]
  void *v17; // [rsp+A8h] [rbp+60h] BYREF

  v14 = 0;
  v17 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  ParameterCount = WdiGetParameterCount(*((_QWORD *)this + 16), &v14);
  if ( ParameterCount >= 0 )
  {
    if ( v14 )
    {
      v6 = 0;
      v7 = 0;
      while ( 1 )
      {
        LODWORD(cb) = 0;
        ParameterCount = CNetDiagClient::GetParamType(this, v7, (enum CNetDiagClient::NdfParamType *)&cb, &v17);
        if ( ParameterCount < 0 )
          break;
        if ( (_DWORD)cb == 1 || (_DWORD)cb == 2 || (_DWORD)cb == 3 || (_DWORD)cb == 4 || (_DWORD)cb == 6 )
        {
          v7 = v14;
        }
        else if ( v7 )
        {
          v6 = (unsigned int)(v6 + 1);
        }
        else
        {
          ParameterCount = CNetDiagClient::ExtractString(
                             (CNetDiagClient *)(unsigned int)(cb - 4),
                             v17,
                             (unsigned __int16 **)this + 3);
          if ( ParameterCount < 0 )
            break;
        }
        if ( ++v7 >= v14 )
        {
          v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v6);
          if ( v8 )
          {
            v2 = v8;
            memset_0(v8, 0, 144 * v6);
            v3 = v6;
            v16 = 1;
            v9 = 1;
            if ( (_DWORD)v6 )
            {
              while ( 1 )
              {
                ParameterCount = CNetDiagClient::GetParamType(this, v9, (enum CNetDiagClient::NdfParamType *)&cb, &v17);
                if ( ParameterCount < 0 )
                  break;
                v13 = v17;
                LODWORD(cb) = 0;
                v10 = 0;
                ParameterCount = WdiGetParameterDataLength(v17, &cb);
                if ( ParameterCount >= 0 && (_DWORD)cb )
                {
                  v11 = CoTaskMemAlloc((unsigned int)cb);
                  v10 = v11;
                  if ( v11 )
                  {
                    ParameterCount = WdiGetParameterData(v13, v11, (unsigned int)cb);
                    if ( ParameterCount >= 0 )
                      ParameterCount = DecodeHelperAttribute(v10, (unsigned int)cb, &v2[v9 - 1]);
                  }
                  else
                  {
                    ParameterCount = -2147024882;
                  }
                }
                CoTaskMemFree(v10);
                if ( ParameterCount < 0 )
                  break;
                if ( ++v9 > (unsigned int)v6 )
                  goto LABEL_29;
              }
              v4 = v16;
            }
            else
            {
LABEL_29:
              _attributes_array_t::FreeAll((CNetDiagClient *)((char *)this + 32));
              *((_DWORD *)this + 8) = v6;
              *((_QWORD *)this + 5) = v2;
              v2 = 0;
              v3 = 0;
              v4 = 0;
            }
          }
          else
          {
            ParameterCount = -2147024882;
          }
          break;
        }
      }
    }
    else
    {
      ParameterCount = -2147467259;
    }
  }
  if ( v2 )
    FreeHelperAttributes(v2, v3, v4);
  return (unsigned int)ParameterCount;
}

```

## disassembly

```asm
0x18000e0c4  push    rbp
0x18000e0c6  push    rbx
0x18000e0c7  push    rsi
0x18000e0c8  push    rdi
0x18000e0c9  push    r12
0x18000e0cb  push    r13
0x18000e0cd  push    r14
0x18000e0cf  push    r15
0x18000e0d1  mov     rbp, rsp
0x18000e0d4  sub     rsp, 48h
0x18000e0d8  mov     r13, rcx
0x18000e0db  mov     [rbp+arg_0], 0
0x18000e0e2  mov     [rbp+arg_18], 0
0x18000e0ea  xor     r14d, r14d
0x18000e0ed  xor     r12d, r12d
0x18000e0f0  xor     r15d, r15d
0x18000e0f3  lea     rdx, [rbp+arg_0]
0x18000e0f7  mov     rcx, [rcx+80h]
0x18000e0fe  call    cs:__imp_WdiGetParameterCount
0x18000e104  mov     edi, eax
0x18000e106  test    eax, eax
0x18000e108  js      loc_18000E2A8
0x18000e10e  mov     eax, [rbp+arg_0]
0x18000e111  test    eax, eax
0x18000e113  jnz     short loc_18000E11F
0x18000e115  mov     edi, 80004005h
0x18000e11a  jmp     loc_18000E2A8
0x18000e11f  xor     esi, esi
0x18000e121  xor     ebx, ebx
0x18000e123  test    eax, eax
0x18000e125  jz      short loc_18000E191
0x18000e127  mov     dword ptr [rbp+cb], 0
0x18000e12e  lea     r9, [rbp+arg_18]; void **
0x18000e132  lea     r8, [rbp+cb]; enum CNetDiagClient::NdfParamType *
0x18000e136  mov     edx, ebx; unsigned int
0x18000e138  mov     rcx, r13; this
0x18000e13b  call    ?GetParamType@CNetDiagClient@@IEAAJIPEAW4NdfParamType@1@PEAPEAX@Z; CNetDiagClient::GetParamType(uint,CNetDiagClient::NdfParamType *,void * *)
0x18000e140  mov     edi, eax
0x18000e142  test    eax, eax
0x18000e144  js      loc_18000E2A8
0x18000e14a  mov     ecx, dword ptr [rbp+cb]
0x18000e14d  sub     ecx, 1
0x18000e150  jz      short loc_18000E187
0x18000e152  sub     ecx, 1
0x18000e155  jz      short loc_18000E187
0x18000e157  sub     ecx, 1
0x18000e15a  jz      short loc_18000E187
0x18000e15c  sub     ecx, 1; this
0x18000e15f  jz      short loc_18000E187
0x18000e161  cmp     ecx, 2
0x18000e164  jz      short loc_18000E187
0x18000e166  test    ebx, ebx
0x18000e168  jnz     short loc_18000E183
0x18000e16a  lea     r8, [r13+18h]; unsigned __int16 **
0x18000e16e  mov     rdx, [rbp+arg_18]; void *
0x18000e172  call    ?ExtractString@CNetDiagClient@@IEAAJPEAXPEAPEAG@Z; CNetDiagClient::ExtractString(void *,ushort * *)
0x18000e177  mov     edi, eax
0x18000e179  test    eax, eax
0x18000e17b  js      loc_18000E2A8
0x18000e181  jmp     short loc_18000E18A
0x18000e183  inc     esi
0x18000e185  jmp     short loc_18000E18A
0x18000e187  mov     ebx, [rbp+arg_0]
0x18000e18a  inc     ebx
0x18000e18c  cmp     ebx, [rbp+arg_0]
0x18000e18f  jb      short loc_18000E127
0x18000e191  lea     rbx, [rsi+rsi*8]
0x18000e195  shl     rbx, 4
0x18000e199  mov     rcx, rbx; cb
0x18000e19c  call    cs:__imp_CoTaskMemAlloc
0x18000e1a2  test    rax, rax
0x18000e1a5  jnz     short loc_18000E1B1
0x18000e1a7  mov     edi, 8007000Eh
0x18000e1ac  jmp     loc_18000E2A8
0x18000e1b1  mov     r14, rax
0x18000e1b4  mov     r8, rbx; Size
0x18000e1b7  xor     edx, edx; Val
0x18000e1b9  mov     rcx, rax; void *
0x18000e1bc  call    memset_0
0x18000e1c1  mov     [rbp+var_20], r14
0x18000e1c5  mov     r12d, esi
0x18000e1c8  mov     [rbp+var_18], esi
0x18000e1cb  mov     eax, 1
0x18000e1d0  mov     [rbp+arg_10], eax
0x18000e1d3  mov     [rbp+var_14], eax
0x18000e1d6  mov     ebx, eax
0x18000e1d8  cmp     esi, eax
0x18000e1da  jb      loc_18000E288
0x18000e1e0  lea     r9, [rbp+arg_18]; void **
0x18000e1e4  lea     r8, [rbp+cb]; enum CNetDiagClient::NdfParamType *
0x18000e1e8  mov     edx, ebx; unsigned int
0x18000e1ea  mov     rcx, r13; this
0x18000e1ed  call    ?GetParamType@CNetDiagClient@@IEAAJIPEAW4NdfParamType@1@PEAPEAX@Z; CNetDiagClient::GetParamType(uint,CNetDiagClient::NdfParamType *,void * *)
0x18000e1f2  mov     edi, eax
0x18000e1f4  test    eax, eax
0x18000e1f6  js      loc_18000E2A4
0x18000e1fc  mov     rax, [rbp+arg_18]
0x18000e200  mov     [rbp+var_28], rax
0x18000e204  mov     dword ptr [rbp+cb], 0
0x18000e20b  xor     r15d, r15d
0x18000e20e  lea     rdx, [rbp+cb]
0x18000e212  mov     rcx, rax
0x18000e215  call    cs:__imp_WdiGetParameterDataLength
0x18000e21b  mov     edi, eax
0x18000e21d  test    eax, eax
0x18000e21f  js      short loc_18000E271
0x18000e221  mov     eax, dword ptr [rbp+cb]
0x18000e224  test    eax, eax
0x18000e226  jz      short loc_18000E271
0x18000e228  mov     ecx, eax; cb
0x18000e22a  call    cs:__imp_CoTaskMemAlloc
0x18000e230  mov     r15, rax
0x18000e233  test    rax, rax
0x18000e236  jnz     short loc_18000E23F
0x18000e238  mov     edi, 8007000Eh
0x18000e23d  jmp     short loc_18000E271
0x18000e23f  mov     r8d, dword ptr [rbp+cb]
0x18000e243  mov     rdx, r15
0x18000e246  mov     rcx, [rbp+var_28]
0x18000e24a  call    cs:__imp_WdiGetParameterData
0x18000e250  mov     edi, eax
0x18000e252  test    eax, eax
0x18000e254  js      short loc_18000E271
0x18000e256  lea     eax, [rbx-1]
0x18000e259  lea     r8, [rax+rax*8]
0x18000e25d  shl     r8, 4
0x18000e261  add     r8, r14
0x18000e264  mov     edx, dword ptr [rbp+cb]
0x18000e267  mov     rcx, r15
0x18000e26a  call    DecodeHelperAttribute
0x18000e26f  mov     edi, eax
0x18000e271  mov     rcx, r15; pv
0x18000e274  call    cs:__imp_CoTaskMemFree
0x18000e27a  test    edi, edi
0x18000e27c  js      short loc_18000E2A4
0x18000e27e  inc     ebx
0x18000e280  cmp     ebx, esi
0x18000e282  jbe     loc_18000E1E0
0x18000e288  lea     rcx, [r13+20h]; this
0x18000e28c  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000e291  mov     [r13+20h], esi
0x18000e295  mov     [r13+28h], r14
0x18000e299  xor     r14d, r14d
0x18000e29c  xor     r12d, r12d
0x18000e29f  xor     r15d, r15d
0x18000e2a2  jmp     short loc_18000E2A8
0x18000e2a4  mov     r15d, [rbp+arg_10]
0x18000e2a8  test    r14, r14
0x18000e2ab  jz      short loc_18000E2BB
0x18000e2ad  mov     r8d, r15d; int
0x18000e2b0  mov     edx, r12d; unsigned int
0x18000e2b3  mov     rcx, r14; pv
0x18000e2b6  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18000e2bb  mov     eax, edi
0x18000e2bd  add     rsp, 48h
0x18000e2c1  pop     r15
0x18000e2c3  pop     r14
0x18000e2c5  pop     r13
0x18000e2c7  pop     r12
0x18000e2c9  pop     rdi
0x18000e2ca  pop     rsi
0x18000e2cb  pop     rbx
0x18000e2cc  pop     rbp
0x18000e2cd  retn
```
