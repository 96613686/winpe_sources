# _AppendWWANProvider(HINSTANCE__ *,uint,uint,ushort const *,int,tagNETCON_PROPERTIES *)

- ea: `0x1800219a4`
- end: `0x180021a33`
- name: `?_AppendWWANProvider@@YAJPEAUHINSTANCE__@@IIPEBGHPEAUtagNETCON_PROPERTIES@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, unsigned int, const unsigned __int16 *, int, struct tagNETCON_PROPERTIES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fde8`

## callees

- `0x180014274`
- `0x1800219a4`
- `0x180021ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219e6`

## pseudocode

```c
__int64 __fastcall _AppendWWANProvider(
        HINSTANCE a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5,
        struct tagNETCON_PROPERTIES *a6)
{
  int v6; // edi
  WCHAR *v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  v6 = ResourceStringCoAllocFormatMessage(a1, (unsigned int)(a5 != 0) + 197, &v8, a6->pszwName, a4);
  if ( v6 >= 0 )
  {
    CoTaskMemFree(a6->pszwName);
    a6->pszwName = v8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800219a4  mov     rax, rsp
0x1800219a7  mov     [rax+8], rbx
0x1800219ab  push    rdi
0x1800219ac  sub     rsp, 40h
0x1800219b0  neg     [rsp+48h+arg_20]
0x1800219b4  lea     r8, [rax-18h]
0x1800219b8  mov     rbx, [rsp+48h+arg_28]
0x1800219bd  sbb     edx, edx
0x1800219bf  mov     [rax-28h], r9
0x1800219c3  neg     edx
0x1800219c5  mov     qword ptr [rax-18h], 0
0x1800219cd  add     edx, 0C5h
0x1800219d3  mov     r9, [rbx+10h]
0x1800219d7  call    ResourceStringCoAllocFormatMessage
0x1800219dc  mov     edi, eax
0x1800219de  test    eax, eax
0x1800219e0  js      short loc_1800219F5
0x1800219e2  mov     rcx, [rbx+10h]; pv
0x1800219e6  call    cs:__imp_CoTaskMemFree
0x1800219ec  mov     rcx, [rsp+48h+var_18]
0x1800219f1  mov     [rbx+10h], rcx
0x1800219f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219fc  lea     rax, WPP_GLOBAL_Control
0x180021a03  cmp     rcx, rax
0x180021a06  jz      short loc_180021A26
0x180021a08  test    byte ptr [rcx+1Ch], 8
0x180021a0c  jz      short loc_180021A26
0x180021a0e  mov     rcx, [rcx+10h]
0x180021a12  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x180021a19  mov     edx, 30h ; '0'
0x180021a1e  mov     r9d, edi
0x180021a21  call    WPP_SF_d
0x180021a26  mov     rbx, [rsp+48h+arg_0]
0x180021a2b  mov     eax, edi
0x180021a2d  add     rsp, 40h
0x180021a31  pop     rdi
0x180021a32  retn
```
