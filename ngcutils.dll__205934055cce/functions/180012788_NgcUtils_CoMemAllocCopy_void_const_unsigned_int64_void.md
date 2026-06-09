# NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)

- ea: `0x180012788`
- end: `0x18001289e`
- name: `?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z`
- size: `278`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, size_t Size, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800104b0`
- `0x180011680`

## callees

- `0x18000113c`
- `0x180003080`
- `0x180003b36`
- `0x180003bc8`
- `0x1800052f5`
- `0x180012788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012811`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127c5`

## pseudocode

```c
__int64 __fastcall NgcUtils::CoMemAllocCopy(NgcUtils *this, size_t Size, _QWORD *a3, void **a4)
{
  _BYTE *v8; // rax
  void *v9; // rbx
  _BYTE *i; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-50h] BYREF
  int *v16; // [rsp+58h] [rbp-30h]
  __int64 v17; // [rsp+60h] [rbp-28h]

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v8 = CoTaskMemAlloc(Size);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  for ( i = &v8[Size]; v8 != i; ++v8 )
    *v8 = 0;
  if ( Size )
  {
    if ( !this )
    {
      memset_0(v9, 0, Size);
      *(_DWORD *)_o__errno(v12, v11, v13) = 22;
      invalid_parameter_noinfo();
      if ( (unsigned int)dword_180075000 > 1 )
      {
        v14 = 22;
        v16 = &v14;
        v17 = 4;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_180075000,
          (unsigned __int8 *)byte_180068659,
          0,
          0,
          3u,
          &v15);
      }
      __fastfail(0x16u);
    }
    memcpy_0(v9, this, Size);
  }
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012788  mov     [rsp+arg_18], rbx
0x18001278d  push    rbp
0x18001278e  push    rsi
0x18001278f  push    rdi
0x180012790  sub     rsp, 70h
0x180012794  mov     rax, cs:__security_cookie
0x18001279b  xor     rax, rsp
0x18001279e  mov     [rsp+88h+var_20], rax
0x1800127a3  mov     rsi, r8
0x1800127a6  mov     rdi, rdx
0x1800127a9  mov     rbp, rcx
0x1800127ac  test    r8, r8
0x1800127af  jnz     short loc_1800127BB
0x1800127b1  mov     eax, 80004003h
0x1800127b6  jmp     loc_180012881
0x1800127bb  mov     rcx, rdi; cb
0x1800127be  mov     qword ptr [r8], 0
0x1800127c5  call    cs:__imp_CoTaskMemAlloc
0x1800127cb  mov     rbx, rax
0x1800127ce  test    rax, rax
0x1800127d1  jz      loc_18001287C
0x1800127d7  lea     rcx, [rax+rdi]
0x1800127db  cmp     rax, rcx
0x1800127de  jz      short loc_1800127EC
0x1800127e0  xor     edx, edx
0x1800127e2  mov     [rax], dl
0x1800127e4  inc     rax
0x1800127e7  cmp     rax, rcx
0x1800127ea  jnz     short loc_1800127E0
0x1800127ec  test    rdi, rdi
0x1800127ef  jz      loc_180012875
0x1800127f5  mov     r8, rdi; Size
0x1800127f8  mov     rcx, rbx; void *
0x1800127fb  test    rbp, rbp
0x1800127fe  jz      short loc_18001280A
0x180012800  mov     rdx, rbp; Src
0x180012803  call    memcpy_0
0x180012808  jmp     short loc_180012875
0x18001280a  xor     edx, edx; Val
0x18001280c  call    memset_0
0x180012811  call    cs:__imp__o__errno
0x180012817  mov     edi, 16h
0x18001281c  mov     [rax], edi
0x18001281e  call    _invalid_parameter_noinfo
0x180012823  mov     eax, cs:dword_180075000
0x180012829  cmp     eax, 1
0x18001282c  jbe     short loc_180012870
0x18001282e  lea     rax, [rsp+88h+var_58]
0x180012833  mov     [rsp+88h+var_58], edi
0x180012837  mov     [rsp+88h+var_30], rax
0x18001283c  lea     rdx, byte_180068659
0x180012843  lea     rax, [rsp+88h+var_50]
0x180012848  mov     [rsp+88h+var_28], 4
0x180012851  mov     [rsp+88h+var_60], rax
0x180012856  lea     rcx, dword_180075000
0x18001285d  xor     r9d, r9d
0x180012860  mov     [rsp+88h+var_68], 3
0x180012868  xor     r8d, r8d
0x18001286b  call    _tlgWriteTransfer_EventWriteTransfer
0x180012870  mov     rcx, rdi
0x180012873  int     29h; Win8: RtlFailFast(ecx)
0x180012875  mov     [rsi], rbx
0x180012878  xor     eax, eax
0x18001287a  jmp     short loc_180012881
0x18001287c  mov     eax, 8007000Eh
0x180012881  mov     rcx, [rsp+88h+var_20]
0x180012886  xor     rcx, rsp; StackCookie
0x180012889  call    __security_check_cookie
0x18001288e  mov     rbx, [rsp+88h+arg_18]
0x180012896  add     rsp, 70h
0x18001289a  pop     rdi
0x18001289b  pop     rsi
0x18001289c  pop     rbp
0x18001289d  retn
```
