# _lambda_f9278c2444ffc8e18e2a499c4cbbeacf_::operator()

- ea: `0x18008082c`
- end: `0x18008099d`
- name: `_lambda_f9278c2444ffc8e18e2a499c4cbbeacf_::operator()`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800809c0`

## callees

- `0x18000fd60`
- `0x180044640`
- `0x180075fa0`
- `0x180076f20`
- `0x18008082c`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180080870`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008088c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180080870`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008088c`
- `msvcp_win!_Mtx_lock` at `0x180080861`
- `msvcp_win!_Mtx_lock` at `0x180080861`
- `msvcp_win!_Mtx_unlock` at `0x180080973`
- `msvcp_win!_Mtx_unlock` at `0x180080973`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800808d9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800808d9`

## pseudocode

```c
int __fastcall lambda_f9278c2444ffc8e18e2a499c4cbbeacf_::operator()(CDXGIOutput ***a1)
{
  CDXGIOutput **v1; // rbx
  CDXGIOutput **v3; // r9
  __int64 v4; // r9
  int v5; // xmm0_4
  int v6; // xmm1_4
  CDXGIOutput **v7; // rdx
  int v8; // xmm0_4
  char v10[100]; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+94h] [rbp-6Ch]
  int v12; // [rsp+98h] [rbp-68h]
  CDXGIOutput *v13; // [rsp+9Ch] [rbp-64h]
  CDXGIOutput *v14; // [rsp+A4h] [rbp-5Ch]
  CDXGIOutput *v15; // [rsp+ACh] [rbp-54h]
  CDXGIOutput *v16; // [rsp+B4h] [rbp-4Ch]
  int v17; // [rsp+BCh] [rbp-44h]
  int v18; // [rsp+C0h] [rbp-40h]
  int v19; // [rsp+C4h] [rbp-3Ch]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+D0h] [rbp-30h] BYREF

  v1 = *a1;
  if ( _Mtx_lock((_Mtx_t)(*a1 + 3)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v1 + 25) == 0x7FFFFFFF )
  {
    *((_DWORD *)v1 + 25) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  memset_0(&requestPacket.adapterId, 0, 0x800u);
  v3 = *a1;
  requestPacket.type = -2;
  requestPacket.size = 2056;
  requestPacket.adapterId = **(LUID **)&CDXGIOutput::GetAdapterLuid(*v3);
  requestPacket.id = *(_DWORD *)(*(_QWORD *)v4 + 256LL);
  if ( !DisplayConfigGetDeviceInfo(&requestPacket) )
  {
    SOutputDesc::SOutputDesc((SOutputDesc *)v10, (struct _DISPLAYCONFIG_GET_DISPLAY_INFO *)&requestPacket, 0, 0);
    v5 = v17;
    v6 = v19;
    *((_DWORD *)*a1 + 52) = v11;
    *((_DWORD *)*a1 + 53) = v12;
    v7 = *a1;
    v7[29] = v15;
    v7[28] = v14;
    v7[27] = v13;
    v7[30] = v16;
    *((_DWORD *)v7 + 62) = v5;
    v8 = v18;
    *((_DWORD *)*a1 + 64) = v6;
    *((_DWORD *)*a1 + 63) = v8;
  }
  return _Mtx_unlock((_Mtx_t)(v1 + 3));
}

```

## disassembly

```asm
0x18008082c  mov     [rsp-8+arg_8], rbx
0x180080831  mov     [rsp-8+arg_10], rdi
0x180080836  push    rbp
0x180080837  lea     rbp, [rsp-7F0h]
0x18008083f  sub     rsp, 8F0h
0x180080846  mov     rax, cs:__security_cookie
0x18008084d  xor     rax, rsp
0x180080850  mov     [rbp+7F0h+var_10], rax
0x180080857  mov     rbx, [rcx]
0x18008085a  mov     rdi, rcx
0x18008085d  lea     rcx, [rbx+18h]; _Mtx_t
0x180080861  call    cs:__imp__Mtx_lock
0x180080867  test    eax, eax
0x180080869  jz      short loc_180080877
0x18008086b  mov     ecx, 5
0x180080870  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180080876  int     3; Trap to Debugger
0x180080877  cmp     dword ptr [rbx+64h], 7FFFFFFFh
0x18008087e  jnz     short loc_180080893
0x180080880  mov     ecx, 6
0x180080885  mov     dword ptr [rbx+64h], 7FFFFFFEh
0x18008088c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180080892  int     3; Trap to Debugger
0x180080893  xor     edx, edx; Val
0x180080895  lea     rcx, [rbp+7F0h+requestPacket.adapterId]; void *
0x180080899  mov     r8d, 800h; Size
0x18008089f  call    memset_0
0x1800808a4  mov     r9, [rdi]
0x1800808a7  lea     rdx, [rsp+8F0h+var_8D0]
0x1800808ac  mov     [rbp+7F0h+requestPacket.type], 0FFFFFFFEh
0x1800808b3  mov     [rbp+7F0h+requestPacket.size], 808h
0x1800808ba  mov     rcx, [r9]; this
0x1800808bd  call    ?GetAdapterLuid@CDXGIOutput@@QEBA?AU_LUID@@XZ; CDXGIOutput::GetAdapterLuid(void)
0x1800808c2  mov     rcx, [rax]
0x1800808c5  mov     qword ptr [rbp+7F0h+requestPacket.adapterId.LowPart], rcx
0x1800808c9  mov     rax, [r9]
0x1800808cc  mov     ecx, [rax+100h]
0x1800808d2  mov     [rbp+7F0h+requestPacket.id], ecx
0x1800808d5  lea     rcx, [rbp+7F0h+requestPacket]; requestPacket
0x1800808d9  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800808df  test    eax, eax
0x1800808e1  jnz     loc_18008096F
0x1800808e7  xor     r9d, r9d; bool
0x1800808ea  lea     rdx, [rbp+7F0h+requestPacket]; struct _DISPLAYCONFIG_GET_DISPLAY_INFO *
0x1800808ee  xor     r8d, r8d; bool
0x1800808f1  lea     rcx, [rsp+8F0h+var_8C0]; this
0x1800808f6  call    ??0SOutputDesc@@QEAA@PEAU_DISPLAYCONFIG_GET_DISPLAY_INFO@@_N1@Z; SOutputDesc::SOutputDesc(_DISPLAYCONFIG_GET_DISPLAY_INFO *,bool,bool)
0x1800808fb  mov     rcx, [rdi]
0x1800808fe  mov     eax, [rbp+7F0h+var_85C]
0x180080901  movss   xmm0, [rbp+7F0h+var_834]
0x180080906  movss   xmm1, [rbp+7F0h+var_82C]
0x18008090b  mov     [rcx+0D0h], eax
0x180080911  mov     rcx, [rdi]
0x180080914  mov     eax, [rbp+7F0h+var_858]
0x180080917  mov     [rcx+0D4h], eax
0x18008091d  mov     rdx, [rdi]
0x180080920  mov     rax, [rbp+7F0h+var_844]
0x180080924  mov     [rdx+0E8h], rax
0x18008092b  mov     rax, [rbp+7F0h+var_84C]
0x18008092f  mov     [rdx+0E0h], rax
0x180080936  mov     rax, [rbp+7F0h+var_854]
0x18008093a  mov     [rdx+0D8h], rax
0x180080941  mov     rax, [rbp+7F0h+var_83C]
0x180080945  mov     [rdx+0F0h], rax
0x18008094c  movss   dword ptr [rdx+0F8h], xmm0
0x180080954  mov     rax, [rdi]
0x180080957  movss   xmm0, [rbp+7F0h+var_830]
0x18008095c  movss   dword ptr [rax+100h], xmm1
0x180080964  mov     rax, [rdi]
0x180080967  movss   dword ptr [rax+0FCh], xmm0
0x18008096f  lea     rcx, [rbx+18h]; _Mtx_t
0x180080973  call    cs:__imp__Mtx_unlock
0x180080979  mov     rcx, [rbp+7F0h+var_10]
0x180080980  xor     rcx, rsp; StackCookie
0x180080983  call    __security_check_cookie
0x180080988  lea     r11, [rsp+8F0h+var_s0]
0x180080990  mov     rbx, [r11+18h]
0x180080994  mov     rdi, [r11+20h]
0x180080998  mov     rsp, r11
0x18008099b  pop     rbp
0x18008099c  retn
```
