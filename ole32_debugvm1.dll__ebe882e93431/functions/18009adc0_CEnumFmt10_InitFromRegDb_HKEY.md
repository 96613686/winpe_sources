# CEnumFmt10::InitFromRegDb(HKEY__ *)

- ea: `0x18009adc0`
- end: `0x18009b01e`
- name: `?InitFromRegDb@CEnumFmt10@@UEAAJPEAUHKEY__@@@Z`
- size: `606`
- prototype: `HRESULT __fastcall(CEnumFmt10 *this, HKEY__ *hkey)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009ab30`

## callees

- `0x180034bfc`
- `0x18009adc0`
- `0x18009b560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009aed7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009aed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009adde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009ade9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009adde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009ade9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009adfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009affc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009adfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009affc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b005`

## string_xrefs

- `0x18009ae29`: `Protocol\StdFileEditing\RequestDataFormats`
- `0x18009ae7b`: `Protocol\StdFileEditing\SetDataFormats`

## pseudocode

```c
__int64 __fastcall CEnumFmt10::InitFromRegDb(CEnumFmt10 *this, HKEY__ *hkey)
{
  wchar_t *v4; // r14
  wchar_t *v5; // rax
  wchar_t *v6; // rsi
  wchar_t *v7; // rcx
  __int64 v9; // rbx
  wchar_t v10; // cx
  wchar_t *v11; // rdx
  bool v12; // zf
  __int64 v13; // rax
  wchar_t v14; // cx
  wchar_t *v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // edi
  FMT *v18; // rax
  unsigned __int64 v19; // rbp
  wchar_t *v20; // rbx
  int v21; // r12d
  wchar_t v22; // ax
  wchar_t *v23; // rcx
  bool v24; // cf
  wchar_t *v25; // rbx
  int v26; // r12d
  wchar_t v27; // ax
  wchar_t *v28; // rcx
  unsigned __int16 v29; // ax
  FMT *m_rgFmt; // rdx
  unsigned __int64 i; // rcx
  unsigned int cb; // [rsp+80h] [rbp+18h] BYREF

  v4 = (wchar_t *)CoTaskMemAlloc(0x400u);
  v5 = (wchar_t *)CoTaskMemAlloc(0x400u);
  v6 = v5;
  if ( !v4 )
  {
    v7 = v5;
LABEL_3:
    CoTaskMemFree(v7);
    return 2147942414LL;
  }
  if ( !v5 )
  {
    v7 = v4;
    goto LABEL_3;
  }
  cb = 1024;
  v9 = 0;
  if ( !wRegQueryValue(hkey, L"Protocol\\StdFileEditing\\RequestDataFormats", v4, &cb) )
  {
    v10 = *v4;
    v9 = 1;
    if ( *v4 )
    {
      v11 = v4;
      do
      {
        v12 = v10 == 44;
        v13 = v9 + 1;
        v10 = *++v11;
        if ( !v12 )
          v13 = v9;
        v9 = v13;
      }
      while ( v10 );
    }
  }
  cb = 1024;
  if ( !wRegQueryValue(hkey, L"Protocol\\StdFileEditing\\SetDataFormats", v6, &cb) )
  {
    v14 = *v6;
    ++v9;
    if ( *v6 )
    {
      v15 = v6;
      do
      {
        v12 = v14 == 44;
        v16 = v9 + 1;
        v14 = *++v15;
        if ( !v12 )
          v16 = v9;
        v9 = v16;
      }
      while ( v14 );
    }
  }
  if ( v9 )
  {
    v18 = (FMT *)HeapAlloc(g_hHeap, 0, 8 * v9 + 8);
    this->m_rgFmt = v18;
    if ( v18 )
    {
      v17 = 0;
      v19 = 0;
      if ( *v4 )
      {
        v20 = v4;
        v21 = 1;
        do
        {
          while ( 1 )
          {
            v22 = *v20;
            if ( *v20 != 32 )
              break;
            ++v20;
          }
          v23 = v20;
          if ( v22 )
          {
            do
            {
              if ( v22 == 44 )
                break;
              v22 = *++v20;
            }
            while ( *v20 );
          }
          v24 = *v20 != 0;
          *v20++ = 0;
          v21 = v24 ? v21 : 0;
          this->m_rgFmt[v19].cf = String2Clipformat(v23);
          this->m_rgFmt[v19++].dw = 1;
        }
        while ( v21 );
      }
      if ( *v6 )
      {
        v25 = v6;
        v26 = 1;
        do
        {
          while ( 1 )
          {
            v27 = *v25;
            if ( *v25 != 32 )
              break;
            ++v25;
          }
          v28 = v25;
          if ( v27 )
          {
            do
            {
              if ( v27 == 44 )
                break;
              v27 = *++v25;
            }
            while ( *v25 );
          }
          v24 = *v25 != 0;
          *v25++ = 0;
          v26 = v24 ? v26 : 0;
          v29 = String2Clipformat(v28);
          m_rgFmt = this->m_rgFmt;
          for ( i = 0; i < v19; ++i )
          {
            if ( m_rgFmt[i].cf == v29 )
            {
              m_rgFmt[i].dw |= 2u;
              goto LABEL_43;
            }
          }
          m_rgFmt[v19].cf = v29;
          this->m_rgFmt[v19++].dw = 2;
LABEL_43:
          ;
        }
        while ( v26 );
      }
      this->m_rgFmt[v19].cf = 0;
      this->m_cFmt = v19;
    }
    else
    {
      v17 = -2147024882;
    }
  }
  else
  {
    v17 = -2147221166;
  }
  CoTaskMemFree(v4);
  CoTaskMemFree(v6);
  return v17;
}

```

## disassembly

```asm
0x18009adc0  push    rbx
0x18009adc2  push    rbp
0x18009adc3  push    rsi
0x18009adc4  push    rdi
0x18009adc5  push    r12
0x18009adc7  push    r13
0x18009adc9  push    r14
0x18009adcb  push    r15
0x18009adcd  sub     rsp, 28h
0x18009add1  mov     r15, this
0x18009add4  mov     ebp, 400h
0x18009add9  mov     ecx, ebp; cb
0x18009addb  mov     rdi, hkey
0x18009adde  call    cs:__imp_CoTaskMemAlloc
0x18009ade4  mov     ecx, ebp; cb
0x18009ade6  mov     r14, rax
0x18009ade9  call    cs:__imp_CoTaskMemAlloc
0x18009adef  xor     r13d, r13d
0x18009adf2  mov     rsi, rax
0x18009adf5  test    r14, r14
0x18009adf8  jnz     short loc_18009AE0D
0x18009adfa  mov     this, rax; pv
0x18009adfd  call    cs:__imp_CoTaskMemFree
0x18009ae03  mov     eax, 8007000Eh
0x18009ae08  jmp     loc_18009B00D
0x18009ae0d  test    rsi, rsi
0x18009ae10  jnz     short loc_18009AE17
0x18009ae12  mov     this, r14
0x18009ae15  jmp     short loc_18009ADFD
0x18009ae17  lea     r9, [rsp+68h+cb]; lpdwSize
0x18009ae1f  mov     [rsp+68h+cb], ebp
0x18009ae26  mov     r8, r14; lpValue
0x18009ae29  lea     hkey, aProtocolStdfil; "Protocol\\StdFileEditing\\RequestDataFo"...
0x18009ae30  mov     this, rdi; hKey
0x18009ae33  mov     rbx, r13
0x18009ae36  call    wRegQueryValue
0x18009ae3b  test    eax, eax
0x18009ae3d  jnz     short loc_18009AE69
0x18009ae3f  movzx   ecx, word ptr [r14]
0x18009ae43  lea     ebx, [rax+1]
0x18009ae46  test    cx, cx
0x18009ae49  jz      short loc_18009AE69
0x18009ae4b  mov     hkey, r14
0x18009ae4e  cmp     cx, 2Ch ; ','
0x18009ae52  lea     rax, [rbx+1]
0x18009ae56  lea     hkey, [hkey+2]
0x18009ae5a  movzx   ecx, word ptr [hkey]
0x18009ae5d  cmovnz  rax, rbx
0x18009ae61  mov     rbx, rax
0x18009ae64  test    cx, cx
0x18009ae67  jnz     short loc_18009AE4E
0x18009ae69  lea     r9, [rsp+68h+cb]; lpdwSize
0x18009ae71  mov     [rsp+68h+cb], ebp
0x18009ae78  mov     r8, rsi; lpValue
0x18009ae7b  lea     hkey, aProtocolStdfil_3; "Protocol\\StdFileEditing\\SetDataFormat"...
0x18009ae82  mov     this, rdi; hKey
0x18009ae85  call    wRegQueryValue
0x18009ae8a  test    eax, eax
0x18009ae8c  jnz     short loc_18009AEB7
0x18009ae8e  movzx   ecx, word ptr [rsi]
0x18009ae91  inc     rbx
0x18009ae94  test    cx, cx
0x18009ae97  jz      short loc_18009AEB7
0x18009ae99  mov     hkey, rsi
0x18009ae9c  cmp     cx, 2Ch ; ','
0x18009aea0  lea     rax, [rbx+1]
0x18009aea4  lea     hkey, [hkey+2]
0x18009aea8  movzx   ecx, word ptr [hkey]
0x18009aeab  cmovnz  rax, rbx
0x18009aeaf  mov     rbx, rax
0x18009aeb2  test    cx, cx
0x18009aeb5  jnz     short loc_18009AE9C
0x18009aeb7  test    rbx, rbx
0x18009aeba  jnz     short loc_18009AEC6
0x18009aebc  mov     edi, 80040152h
0x18009aec1  jmp     $errRtn_147
0x18009aec6  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009aecd  lea     r8, ds:8[rbx*8]; dwBytes
0x18009aed5  xor     edx, edx; dwFlags
0x18009aed7  call    cs:__imp_HeapAlloc
0x18009aedd  mov     [r15+18h], rax
0x18009aee1  test    rax, rax
0x18009aee4  jnz     short loc_18009AEF0
0x18009aee6  mov     edi, 8007000Eh
0x18009aeeb  jmp     $errRtn_147
0x18009aef0  mov     edi, r13d
0x18009aef3  mov     rbp, r13
0x18009aef6  cmp     [r14], r13w
0x18009aefa  jz      short loc_18009AF62
0x18009aefc  mov     rbx, r14
0x18009aeff  mov     r12d, 1
0x18009af05  jmp     short loc_18009AF0B
0x18009af07  add     rbx, 2
0x18009af0b  movzx   eax, word ptr [rbx]
0x18009af0e  cmp     ax, 20h ; ' '
0x18009af12  jz      short loc_18009AF07
0x18009af14  mov     this, rbx; sz
0x18009af17  test    ax, ax
0x18009af1a  jz      short loc_18009AF2E
0x18009af1c  cmp     ax, 2Ch ; ','
0x18009af20  jz      short loc_18009AF2E
0x18009af22  add     rbx, 2
0x18009af26  movzx   eax, word ptr [rbx]
0x18009af29  test    ax, ax
0x18009af2c  jnz     short loc_18009AF1C
0x18009af2e  movzx   eax, word ptr [rbx]
0x18009af31  neg     ax
0x18009af34  mov     [rbx], r13w
0x18009af38  sbb     edx, edx
0x18009af3a  add     rbx, 2
0x18009af3e  and     r12d, edx
0x18009af41  call    String2Clipformat
0x18009af46  mov     this, [r15+18h]
0x18009af4a  mov     [this+rbp*8], ax
0x18009af4e  mov     rax, [r15+18h]
0x18009af52  mov     dword ptr [rax+rbp*8+4], 1
0x18009af5a  inc     rbp
0x18009af5d  test    r12d, r12d
0x18009af60  jnz     short loc_18009AF0B
0x18009af62  cmp     [rsi], r13w
0x18009af66  jz      loc_18009AFEC
0x18009af6c  mov     rbx, rsi
0x18009af6f  mov     r12d, 1
0x18009af75  jmp     short loc_18009AF7B
0x18009af77  add     rbx, 2
0x18009af7b  movzx   eax, word ptr [rbx]
0x18009af7e  cmp     ax, 20h ; ' '
0x18009af82  jz      short loc_18009AF77
0x18009af84  mov     this, rbx; sz
0x18009af87  test    ax, ax
0x18009af8a  jz      short loc_18009AF9E
0x18009af8c  cmp     ax, 2Ch ; ','
0x18009af90  jz      short loc_18009AF9E
0x18009af92  add     rbx, 2
0x18009af96  movzx   eax, word ptr [rbx]
0x18009af99  test    ax, ax
0x18009af9c  jnz     short loc_18009AF8C
0x18009af9e  movzx   eax, word ptr [rbx]
0x18009afa1  neg     ax
0x18009afa4  mov     [rbx], r13w
0x18009afa8  sbb     edx, edx
0x18009afaa  add     rbx, 2
0x18009afae  and     r12d, edx
0x18009afb1  call    String2Clipformat
0x18009afb6  mov     hkey, [r15+18h]
0x18009afba  mov     this, r13
0x18009afbd  cmp     this, rbp
0x18009afc0  jnb     short loc_18009AFD4
0x18009afc2  cmp     [hkey+this*8], ax
0x18009afc6  jz      short loc_18009AFCD
0x18009afc8  inc     this
0x18009afcb  jmp     short loc_18009AFBD
0x18009afcd  or      dword ptr [hkey+this*8+4], 2
0x18009afd2  jmp     short loc_18009AFE7
0x18009afd4  mov     [hkey+rbp*8], ax
0x18009afd8  mov     rax, [r15+18h]
0x18009afdc  mov     dword ptr [rax+rbp*8+4], 2
0x18009afe4  inc     rbp
0x18009afe7  test    r12d, r12d
0x18009afea  jnz     short loc_18009AF7B
0x18009afec  mov     hkey, [r15+18h]
0x18009aff0  mov     [hkey+rbp*8], r13w
0x18009aff5  mov     [r15+20h], rbp
0x18009aff9  mov     this, r14; pv
0x18009affc  call    cs:__imp_CoTaskMemFree
0x18009b002  mov     this, rsi; pv
0x18009b005  call    cs:__imp_CoTaskMemFree
0x18009b00b  mov     eax, edi
0x18009b00d  add     rsp, 28h
0x18009b011  pop     r15
0x18009b013  pop     r14
0x18009b015  pop     r13
0x18009b017  pop     r12
0x18009b019  pop     rdi
0x18009b01a  pop     rsi
0x18009b01b  pop     rbp
0x18009b01c  pop     rbx
0x18009b01d  retn
```
