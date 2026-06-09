# CEnhancedStorageAct::GetDeviceName(ushort * *)

- ea: `0x1800028f0`
- end: `0x18000298c`
- name: `?GetDeviceName@CEnhancedStorageAct@@UEAAJPEAPEAG@Z`
- size: `156`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800028f0`
- `0x180003ce0`
- `0x18000c4b6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002953`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageAct::GetDeviceName(CEnhancedStorageAct *this, unsigned __int16 **a2)
{
  __int64 result; // rax
  int v5; // eax
  SIZE_T v6; // rbp
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi

  if ( a2 )
  {
    v5 = *((_DWORD *)this + 157);
    if ( v5 )
    {
      v6 = (unsigned int)(2 * v5 + 2);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
      v8 = v7;
      if ( v7 )
      {
        memcpy_0(v7, (char *)this + 104, (unsigned int)v6);
        result = 0;
        *a2 = v8;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 2147500033LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
        "ppwszDeviceName");
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800028f0  push    rbx
0x1800028f2  push    rbp
0x1800028f3  push    rsi
0x1800028f4  push    rdi
0x1800028f5  sub     rsp, 28h
0x1800028f9  mov     rdi, rdx
0x1800028fc  mov     rbx, rcx
0x1800028ff  test    rdx, rdx
0x180002902  jnz     short loc_18000293E
0x180002904  mov     rcx, cs:WPP_GLOBAL_Control
0x18000290b  lea     rax, WPP_GLOBAL_Control
0x180002912  cmp     rcx, rax
0x180002915  jz      short loc_180002937
0x180002917  test    byte ptr [rcx+1Ch], 2
0x18000291b  jz      short loc_180002937
0x18000291d  mov     rcx, [rcx+10h]
0x180002921  lea     edx, [rdi+29h]
0x180002924  lea     r9, aPpwszdevicenam; "ppwszDeviceName"
0x18000292b  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002932  call    WPP_SF_s
0x180002937  mov     eax, 80070057h
0x18000293c  jmp     short loc_180002983
0x18000293e  mov     eax, [rcx+274h]
0x180002944  test    eax, eax
0x180002946  jz      short loc_18000297E
0x180002948  lea     eax, ds:2[rax*2]
0x18000294f  mov     ecx, eax; cb
0x180002951  mov     ebp, eax
0x180002953  call    cs:__imp_CoTaskMemAlloc
0x180002959  mov     rsi, rax
0x18000295c  test    rax, rax
0x18000295f  jz      short loc_180002977
0x180002961  lea     rdx, [rbx+68h]; Src
0x180002965  mov     r8d, ebp; Size
0x180002968  mov     rcx, rax; void *
0x18000296b  call    memcpy_0
0x180002970  xor     eax, eax
0x180002972  mov     [rdi], rsi
0x180002975  jmp     short loc_180002983
0x180002977  mov     eax, 8007000Eh
0x18000297c  jmp     short loc_180002983
0x18000297e  mov     eax, 80004001h
0x180002983  add     rsp, 28h
0x180002987  pop     rdi
0x180002988  pop     rsi
0x180002989  pop     rbp
0x18000298a  pop     rbx
0x18000298b  retn
```
