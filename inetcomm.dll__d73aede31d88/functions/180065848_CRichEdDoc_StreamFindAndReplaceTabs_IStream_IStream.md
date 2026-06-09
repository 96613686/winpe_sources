# CRichEdDoc::StreamFindAndReplaceTabs(IStream *,IStream *)

- ea: `0x180065848`
- end: `0x18006598d`
- name: `?StreamFindAndReplaceTabs@CRichEdDoc@@AEAAXPEAUIStream@@0@Z`
- size: `325`
- prototype: `void __fastcall(CRichEdDoc *__hidden this, struct IStream *, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180065520`

## callees

- `0x180065848`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`

## import_xrefs

- `SHLWAPI!__imp_IStream_Read` at `0x1800658df`
- `SHLWAPI!__imp_IStream_Read` at `0x1800658df`
- `SHLWAPI!__imp_IStream_Write` at `0x180065915`
- `SHLWAPI!__imp_IStream_Write` at `0x18006592d`
- `SHLWAPI!__imp_IStream_Write` at `0x180065953`
- `SHLWAPI!__imp_IStream_Write` at `0x180065915`
- `SHLWAPI!__imp_IStream_Write` at `0x18006592d`
- `SHLWAPI!__imp_IStream_Write` at `0x180065953`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800658a2`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800658bd`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800658a2`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800658bd`
- `SHLWAPI!__imp_IStream_Size` at `0x1800658b0`
- `SHLWAPI!__imp_IStream_Size` at `0x1800658b0`

## pseudocode

```c
void __fastcall CRichEdDoc::StreamFindAndReplaceTabs(CRichEdDoc *this, struct IStream *a2, struct IStream *a3)
{
  unsigned int v5; // ebx
  DWORD LowPart; // edi
  ULONG v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // r8d
  unsigned int v10; // ebp
  ULARGE_INTEGER pui; // [rsp+20h] [rbp-2058h] BYREF
  _WORD pv[4104]; // [rsp+30h] [rbp-2048h] BYREF

  v5 = 4098;
  memset_0(pv, 0, 0x2004u);
  pui.QuadPart = 0;
  IStream_Reset(a2);
  IStream_Size(a2, &pui);
  LowPart = pui.LowPart;
  IStream_Reset(a3);
  for ( ; LowPart; LowPart -= v5 )
  {
    v7 = LowPart;
    if ( LowPart >= v5 )
      v7 = v5;
    v5 = v7;
    IStream_Read(a2, pv, v7);
    v8 = 0;
    v9 = 0;
    if ( v5 >> 1 )
    {
      do
      {
        v10 = v9 + 1;
        if ( pv[v9] == 9 )
        {
          IStream_Write(a3, &pv[v8], 2 * (v9 - v8));
          v8 = v10;
          IStream_Write(a3, L"    ", 8u);
        }
        v9 = v10;
      }
      while ( v10 < v5 >> 1 );
      if ( v10 > v8 )
        IStream_Write(a3, &pv[v8], 2 * (v10 - v8));
    }
  }
}

```

## disassembly

```asm
0x180065848  mov     [rsp+arg_0], rbx
0x18006584d  mov     [rsp+arg_18], rbp
0x180065852  push    rsi
0x180065853  push    rdi
0x180065854  push    r12
0x180065856  push    r14
0x180065858  push    r15
0x18006585a  mov     eax, 2050h
0x18006585f  call    _alloca_probe
0x180065864  sub     rsp, rax
0x180065867  mov     rax, cs:__security_cookie
0x18006586e  xor     rax, rsp
0x180065871  mov     [rsp+2078h+var_38], rax
0x180065879  mov     r15, r8
0x18006587c  lea     rcx, [rsp+2078h+pv]; void *
0x180065881  mov     r12, rdx
0x180065884  mov     r8d, 2004h; Size
0x18006588a  xor     edx, edx; Val
0x18006588c  mov     ebx, 1002h
0x180065891  call    memset_0
0x180065896  mov     rcx, r12; pstm
0x180065899  mov     qword ptr [rsp+2078h+pui], 0
0x1800658a2  call    cs:__imp_IStream_Reset
0x1800658a8  lea     rdx, [rsp+2078h+pui]; pui
0x1800658ad  mov     rcx, r12; pstm
0x1800658b0  call    cs:__imp_IStream_Size
0x1800658b6  mov     edi, dword ptr [rsp+2078h+pui]
0x1800658ba  mov     rcx, r15; pstm
0x1800658bd  call    cs:__imp_IStream_Reset
0x1800658c3  test    edi, edi
0x1800658c5  jz      loc_180065961
0x1800658cb  cmp     edi, ebx
0x1800658cd  lea     rdx, [rsp+2078h+pv]; pv
0x1800658d2  mov     eax, edi
0x1800658d4  mov     rcx, r12; pstm
0x1800658d7  cmovnb  eax, ebx
0x1800658da  mov     r8d, eax; cb
0x1800658dd  mov     ebx, eax
0x1800658df  call    cs:__imp_IStream_Read
0x1800658e5  xor     esi, esi
0x1800658e7  mov     r14d, ebx
0x1800658ea  shr     r14d, 1
0x1800658ed  mov     r8d, esi
0x1800658f0  jz      short loc_180065959
0x1800658f2  mov     eax, r8d
0x1800658f5  lea     ebp, [r8+1]
0x1800658f9  cmp     [rsp+rax*2+2078h+pv], 9
0x1800658ff  jnz     short loc_180065933
0x180065901  mov     eax, esi
0x180065903  lea     rdx, [rsp+2078h+pv]
0x180065908  sub     r8d, esi
0x18006590b  mov     rcx, r15; pstm
0x18006590e  add     r8d, r8d; cb
0x180065911  lea     rdx, [rdx+rax*2]; pv
0x180065915  call    cs:__imp_IStream_Write
0x18006591b  mov     r8d, 8; cb
0x180065921  lea     rdx, asc_1800DBF28; "    "
0x180065928  mov     rcx, r15; pstm
0x18006592b  mov     esi, ebp
0x18006592d  call    cs:__imp_IStream_Write
0x180065933  mov     r8d, ebp
0x180065936  cmp     ebp, r14d
0x180065939  jb      short loc_1800658F2
0x18006593b  cmp     ebp, esi
0x18006593d  jbe     short loc_180065959
0x18006593f  mov     eax, esi
0x180065941  lea     rdx, [rsp+2078h+pv]
0x180065946  sub     r8d, esi
0x180065949  mov     rcx, r15; pstm
0x18006594c  add     r8d, r8d; cb
0x18006594f  lea     rdx, [rdx+rax*2]; pv
0x180065953  call    cs:__imp_IStream_Write
0x180065959  sub     edi, ebx
0x18006595b  jnz     loc_1800658CB
0x180065961  mov     rcx, [rsp+2078h+var_38]
0x180065969  xor     rcx, rsp; StackCookie
0x18006596c  call    __security_check_cookie
0x180065971  lea     r11, [rsp+2078h+var_28]
0x180065979  mov     rbx, [r11+30h]
0x18006597d  mov     rbp, [r11+48h]
0x180065981  mov     rsp, r11
0x180065984  pop     r15
0x180065986  pop     r14
0x180065988  pop     r12
0x18006598a  pop     rdi
0x18006598b  pop     rsi
0x18006598c  retn
```
