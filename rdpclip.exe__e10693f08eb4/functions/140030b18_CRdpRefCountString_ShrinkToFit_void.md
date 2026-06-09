# CRdpRefCountString::ShrinkToFit(void)

- ea: `0x140030b18`
- end: `0x140030c91`
- name: `?ShrinkToFit@CRdpRefCountString@@QEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(CRdpRefCountString *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140035550`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x140008c9c`
- `0x140011054`
- `0x1400188b0`
- `0x140030b18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140030bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140030bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030c79`

## string_xrefs

- `0x140030bf2`: `"CoTaskMemAlloc()"`
- `0x140030c69`: `StringCchCopy() failed`

## pseudocode

```c
__int64 __fastcall CRdpRefCountString::ShrinkToFit(const unsigned __int16 **this)
{
  unsigned __int64 v1; // rdx
  int v3; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbp
  unsigned int v10; // eax
  unsigned __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((unsigned int *)this + 12);
  v12 = 0;
  v3 = StringCchLengthW(this[7], v1, &v12);
  if ( v3 >= 0 )
  {
    v7 = v12 + 1;
    if ( v12 + 1 >= *((unsigned int *)this + 12) )
      return (unsigned int)v3;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
    v9 = v8;
    if ( v8 )
    {
      v3 = StringCchCopyW(v8, v7, this[7]);
      if ( v3 >= 0 )
      {
        CoTaskMemFree((LPVOID)this[7]);
        this[7] = v9;
        *((_DWORD *)this + 12) = v7;
        return (unsigned int)v3;
      }
      CoTaskMemFree(v9);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 18;
        v6 = "StringCchCopy() failed";
        goto LABEL_6;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_bf5708d4aab731b2082d37f18983ea55_Traceguids,
          v10,
          (__int64)"\"CoTaskMemAlloc()\"");
      }
      return (unsigned int)-2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 16;
    v6 = "StringCchLength() failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_bf5708d4aab731b2082d37f18983ea55_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140030b18  push    rbx
0x140030b1a  push    rbp
0x140030b1b  push    rsi
0x140030b1c  push    rdi
0x140030b1d  sub     rsp, 38h
0x140030b21  mov     edx, [rcx+30h]; unsigned __int64
0x140030b24  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x140030b29  mov     rdi, rcx
0x140030b2c  mov     [rsp+58h+arg_0], 0
0x140030b35  mov     rcx, [rcx+38h]; unsigned __int16 *
0x140030b39  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140030b3e  mov     esi, eax
0x140030b40  test    eax, eax
0x140030b42  jns     short loc_140030BA8
0x140030b44  mov     rax, cs:WPP_GLOBAL_Control
0x140030b4b  lea     rcx, WPP_GLOBAL_Control
0x140030b52  cmp     rax, rcx
0x140030b55  jz      loc_140030C86
0x140030b5b  test    byte ptr [rax+1Ch], 8
0x140030b5f  jz      loc_140030C86
0x140030b65  cmp     byte ptr [rax+19h], 2
0x140030b69  jb      loc_140030C86
0x140030b6f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140030b74  mov     edx, 10h
0x140030b79  lea     rcx, aStringcchlengt_1; "StringCchLength() failed"
0x140030b80  mov     [rsp+58h+var_30], esi
0x140030b84  lea     r8, WPP_bf5708d4aab731b2082d37f18983ea55_Traceguids
0x140030b8b  mov     [rsp+58h+var_38], rcx
0x140030b90  mov     r9d, eax
0x140030b93  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b9a  mov     rcx, [rcx+10h]
0x140030b9e  call    WPP_SF_DsD
0x140030ba3  jmp     loc_140030C86
0x140030ba8  mov     rbx, [rsp+58h+arg_0]
0x140030bad  mov     eax, [rdi+30h]
0x140030bb0  inc     rbx
0x140030bb3  cmp     rbx, rax
0x140030bb6  jnb     loc_140030C86
0x140030bbc  lea     rcx, [rbx+rbx]; cb
0x140030bc0  call    cs:__imp_CoTaskMemAlloc
0x140030bc6  mov     rbp, rax
0x140030bc9  test    rax, rax
0x140030bcc  jnz     short loc_140030C22
0x140030bce  mov     rax, cs:WPP_GLOBAL_Control
0x140030bd5  lea     rcx, WPP_GLOBAL_Control
0x140030bdc  cmp     rax, rcx
0x140030bdf  jz      short loc_140030C1B
0x140030be1  test    byte ptr [rax+1Ch], 8
0x140030be5  jz      short loc_140030C1B
0x140030be7  cmp     byte ptr [rax+19h], 2
0x140030beb  jb      short loc_140030C1B
0x140030bed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140030bf2  lea     rcx, aCotaskmemalloc_1; "\"CoTaskMemAlloc()\""
0x140030bf9  mov     r9d, eax
0x140030bfc  mov     [rsp+58h+var_38], rcx
0x140030c01  lea     edx, [rbp+11h]
0x140030c04  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c0b  lea     r8, WPP_bf5708d4aab731b2082d37f18983ea55_Traceguids
0x140030c12  mov     rcx, [rcx+10h]
0x140030c16  call    WPP_SF_Ds
0x140030c1b  mov     esi, 8007000Eh
0x140030c20  jmp     short loc_140030C86
0x140030c22  mov     r8, [rdi+38h]; unsigned __int16 *
0x140030c26  mov     rdx, rbx; unsigned __int64
0x140030c29  mov     rcx, rbp; unsigned __int16 *
0x140030c2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140030c31  mov     esi, eax
0x140030c33  test    eax, eax
0x140030c35  jns     short loc_140030C75
0x140030c37  mov     rcx, rbp; pv
0x140030c3a  call    cs:__imp_CoTaskMemFree
0x140030c40  mov     rax, cs:WPP_GLOBAL_Control
0x140030c47  lea     rcx, WPP_GLOBAL_Control
0x140030c4e  cmp     rax, rcx
0x140030c51  jz      short loc_140030C86
0x140030c53  test    byte ptr [rax+1Ch], 8
0x140030c57  jz      short loc_140030C86
0x140030c59  cmp     byte ptr [rax+19h], 2
0x140030c5d  jb      short loc_140030C86
0x140030c5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140030c64  mov     edx, 12h
0x140030c69  lea     rcx, aStringcchcopyF_0; "StringCchCopy() failed"
0x140030c70  jmp     loc_140030B80
0x140030c75  mov     rcx, [rdi+38h]; pv
0x140030c79  call    cs:__imp_CoTaskMemFree
0x140030c7f  mov     [rdi+38h], rbp
0x140030c83  mov     [rdi+30h], ebx
0x140030c86  mov     eax, esi
0x140030c88  add     rsp, 38h
0x140030c8c  pop     rdi
0x140030c8d  pop     rsi
0x140030c8e  pop     rbp
0x140030c8f  pop     rbx
0x140030c90  retn
```
