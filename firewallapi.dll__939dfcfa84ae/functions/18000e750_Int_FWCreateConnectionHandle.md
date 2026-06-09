# Int_FWCreateConnectionHandle

- ea: `0x18000e750`
- end: `0x18000ea03`
- name: `Int_FWCreateConnectionHandle`
- size: `691`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d0f0`
- `0x18000f0a0`
- `0x180052950`

## callees

- `0x180005e0c`
- `0x18000e750`
- `0x18000ea10`
- `0x18000ecb0`
- `0x1800294b0`
- `0x18003336c`
- `0x180054db8`
- `0x180055378`
- `0x1800554e4`

## import_xrefs

- `fwbase!FwIsMachineLocalHost` at `0x18000e81a`
- `fwbase!FwIsMachineLocalHost` at `0x18000e81a`
- `fwbase!FwHResultToWindowsError` at `0x18000e7f3`
- `fwbase!FwHResultToWindowsError` at `0x18000e7f3`
- `fwbase!FwStringCopy` at `0x18000e7e5`
- `fwbase!FwStringCopy` at `0x18000e7e5`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18000e8db`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18000e8db`

## pseudocode

```c
__int64 __fastcall Int_FWCreateConnectionHandle(
        __int16 a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6)
{
  FwPolicy2 *v10; // rcx
  unsigned int v11; // eax
  __int64 result; // rax
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // [rsp+20h] [rbp-38h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 348, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v16 = 0;
  if ( !a6 )
  {
    v13 = 87;
    if ( v10 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_11;
    v14 = 349;
    v15 = 87;
    goto LABEL_38;
  }
  *(_OWORD *)a6 = 0;
  *(_OWORD *)(a6 + 16) = 0;
  *(_OWORD *)(a6 + 32) = 0;
  *(_OWORD *)(a6 + 48) = 0;
  *(_OWORD *)(a6 + 64) = 0;
  *(_WORD *)a6 = a1;
  *(_DWORD *)(a6 + 72) = a5;
  *(_DWORD *)(a6 + 16) = a3;
  *(_DWORD *)(a6 + 20) = a4;
  v11 = FwStringCopy(a2, a6 + 8);
  LODWORD(result) = FwHResultToWindowsError(v11);
  v13 = result;
  if ( (_DWORD)result )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    v14 = 350;
    goto LABEL_37;
  }
  if ( a3 == 6 )
  {
    LODWORD(result) = LoadGPExtensionDll();
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 351;
    }
    else
    {
      *(_DWORD *)(a6 + 4) = 2;
      LODWORD(result) = Int_FWOpenGPOPolicyStore(a6);
      v13 = result;
      if ( (_DWORD)result )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        v14 = 352;
      }
      else
      {
        result = Int_FWCloseGPOPolicyStore(a6, (a5 >> 3) & 1);
        v13 = result;
        if ( !(_DWORD)result )
          return result;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        v14 = 353;
      }
    }
LABEL_37:
    v15 = (unsigned int)result;
LABEL_38:
    WPP_SF_d(*((_QWORD *)v10 + 2), v14, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v15);
LABEL_11:
    Int_FWClientHandleCleanup(a6);
    return v13;
  }
  FwIsMachineLocalHost(a2, &v16);
  if ( !a2 || v16 == 1 )
  {
    *(_DWORD *)(a6 + 4) = 0;
    result = Int_FWLocalRpcBindingCreate((RPC_BINDING_HANDLE *)(a6 + 32));
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 354;
      goto LABEL_37;
    }
  }
  else
  {
    *(_DWORD *)(a6 + 4) = 1;
    result = Int_FWRemoteRpcBindingCreate(a2);
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 355;
      goto LABEL_37;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e750  mov     [rsp+arg_0], rbx
0x18000e755  mov     [rsp+arg_10], rbp
0x18000e75a  push    rsi
0x18000e75b  push    rdi
0x18000e75c  push    r12
0x18000e75e  push    r14
0x18000e760  push    r15
0x18000e762  sub     rsp, 30h
0x18000e766  mov     rax, cs:__security_cookie
0x18000e76d  xor     rax, rsp
0x18000e770  mov     [rsp+58h+var_30], rax
0x18000e775  mov     rbx, [rsp+58h+arg_28]
0x18000e77d  mov     edi, r9d
0x18000e780  mov     ebp, r8d
0x18000e783  mov     rsi, rdx
0x18000e786  movzx   r14d, cx
0x18000e78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e791  lea     r12, WPP_GLOBAL_Control
0x18000e798  cmp     rcx, r12
0x18000e79b  jnz     loc_18000E86B
0x18000e7a1  xor     r15d, r15d
0x18000e7a4  mov     [rsp+58h+var_38], r15d
0x18000e7a9  test    rbx, rbx
0x18000e7ac  jz      loc_18000E896
0x18000e7b2  xorps   xmm0, xmm0
0x18000e7b5  lea     rdx, [rbx+8]
0x18000e7b9  movups  xmmword ptr [rbx], xmm0
0x18000e7bc  mov     rcx, rsi
0x18000e7bf  movups  xmmword ptr [rbx+10h], xmm0
0x18000e7c3  movups  xmmword ptr [rbx+20h], xmm0
0x18000e7c7  movups  xmmword ptr [rbx+30h], xmm0
0x18000e7cb  movups  xmmword ptr [rbx+40h], xmm0
0x18000e7cf  mov     [rbx], r14w
0x18000e7d3  mov     r14d, [rsp+58h+arg_20]
0x18000e7db  mov     [rbx+48h], r14d
0x18000e7df  mov     [rbx+10h], ebp
0x18000e7e2  mov     [rbx+14h], edi
0x18000e7e5  call    cs:__imp_FwStringCopy
0x18000e7ec  nop     dword ptr [rax+rax+00h]
0x18000e7f1  mov     ecx, eax
0x18000e7f3  call    cs:__imp_FwHResultToWindowsError
0x18000e7fa  nop     dword ptr [rax+rax+00h]
0x18000e7ff  mov     edi, eax
0x18000e801  test    eax, eax
0x18000e803  jnz     loc_18000E8BF
0x18000e809  cmp     ebp, 6
0x18000e80c  jz      loc_18000E8DB
0x18000e812  lea     rdx, [rsp+58h+var_38]
0x18000e817  mov     rcx, rsi
0x18000e81a  call    cs:__imp_FwIsMachineLocalHost
0x18000e821  nop     dword ptr [rax+rax+00h]
0x18000e826  test    rsi, rsi
0x18000e829  jnz     loc_18000E983
0x18000e82f  lea     rcx, [rbx+20h]
0x18000e833  mov     [rbx+4], r15d
0x18000e837  call    Int_FWLocalRpcBindingCreate
0x18000e83c  mov     edi, eax
0x18000e83e  test    eax, eax
0x18000e840  jnz     loc_18000E9CC
0x18000e846  mov     rcx, [rsp+58h+var_30]
0x18000e84b  xor     rcx, rsp; StackCookie
0x18000e84e  call    __security_check_cookie
0x18000e853  mov     rbx, [rsp+58h+arg_0]
0x18000e858  mov     rbp, [rsp+58h+arg_10]
0x18000e85d  add     rsp, 30h
0x18000e861  pop     r15
0x18000e863  pop     r14
0x18000e865  pop     r12
0x18000e867  pop     rdi
0x18000e868  pop     rsi
0x18000e869  retn
0x18000e86b  test    byte ptr [rcx+1Ch], 8
0x18000e86f  jz      loc_18000E7A1
0x18000e875  mov     rcx, [rcx+10h]
0x18000e879  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000e880  mov     edx, 15Ch
0x18000e885  call    WPP_SF_
0x18000e88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e891  jmp     loc_18000E7A1
0x18000e896  mov     edi, 57h ; 'W'
0x18000e89b  cmp     rcx, r12
0x18000e89e  jnz     short loc_18000E8AC
0x18000e8a0  mov     rcx, rbx
0x18000e8a3  call    Int_FWClientHandleCleanup
0x18000e8a8  mov     eax, edi
0x18000e8aa  jmp     short loc_18000E846
0x18000e8ac  test    byte ptr [rcx+1Ch], 1
0x18000e8b0  jz      short loc_18000E8A0
0x18000e8b2  mov     edx, 15Dh
0x18000e8b7  mov     r9d, edi
0x18000e8ba  jmp     loc_18000E9EE
0x18000e8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8c6  cmp     rcx, r12
0x18000e8c9  jz      short loc_18000E8A0
0x18000e8cb  test    byte ptr [rcx+1Ch], 1
0x18000e8cf  jz      short loc_18000E8A0
0x18000e8d1  mov     edx, 15Eh
0x18000e8d6  jmp     loc_18000E9EB
0x18000e8db  call    cs:__imp_LoadGPExtensionDll
0x18000e8e2  nop     dword ptr [rax+rax+00h]
0x18000e8e7  mov     edi, eax
0x18000e8e9  test    eax, eax
0x18000e8eb  jz      short loc_18000E909
0x18000e8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8f4  cmp     rcx, r12
0x18000e8f7  jz      short loc_18000E8A0
0x18000e8f9  test    byte ptr [rcx+1Ch], 1
0x18000e8fd  jz      short loc_18000E8A0
0x18000e8ff  mov     edx, 15Fh
0x18000e904  jmp     loc_18000E9EB
0x18000e909  mov     rcx, rbx
0x18000e90c  mov     dword ptr [rbx+4], 2
0x18000e913  call    Int_FWOpenGPOPolicyStore
0x18000e918  mov     edi, eax
0x18000e91a  test    eax, eax
0x18000e91c  jz      short loc_18000E942
0x18000e91e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e925  cmp     rcx, r12
0x18000e928  jz      loc_18000E8A0
0x18000e92e  test    byte ptr [rcx+1Ch], 1
0x18000e932  jz      loc_18000E8A0
0x18000e938  mov     edx, 160h
0x18000e93d  jmp     loc_18000E9EB
0x18000e942  shr     r14d, 3
0x18000e946  xor     r8d, r8d
0x18000e949  and     r14d, 1
0x18000e94d  mov     rcx, rbx
0x18000e950  mov     edx, r14d
0x18000e953  call    Int_FWCloseGPOPolicyStore
0x18000e958  mov     edi, eax
0x18000e95a  test    eax, eax
0x18000e95c  jz      loc_18000E846
0x18000e962  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e969  cmp     rcx, r12
0x18000e96c  jz      loc_18000E8A0
0x18000e972  test    byte ptr [rcx+1Ch], 1
0x18000e976  jz      loc_18000E8A0
0x18000e97c  mov     edx, 161h
0x18000e981  jmp     short loc_18000E9EB
0x18000e983  cmp     [rsp+58h+var_38], 1
0x18000e988  jz      loc_18000E82F
0x18000e98e  lea     rdx, [rbx+20h]
0x18000e992  mov     dword ptr [rbx+4], 1
0x18000e999  mov     rcx, rsi; NetworkAddr
0x18000e99c  call    Int_FWRemoteRpcBindingCreate
0x18000e9a1  mov     edi, eax
0x18000e9a3  test    eax, eax
0x18000e9a5  jz      loc_18000E846
0x18000e9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b2  cmp     rcx, r12
0x18000e9b5  jz      loc_18000E8A0
0x18000e9bb  test    byte ptr [rcx+1Ch], 1
0x18000e9bf  jz      loc_18000E8A0
0x18000e9c5  mov     edx, 163h
0x18000e9ca  jmp     short loc_18000E9EB
0x18000e9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9d3  cmp     rcx, r12
0x18000e9d6  jz      loc_18000E8A0
0x18000e9dc  test    byte ptr [rcx+1Ch], 1
0x18000e9e0  jz      loc_18000E8A0
0x18000e9e6  mov     edx, 162h
0x18000e9eb  mov     r9d, eax
0x18000e9ee  mov     rcx, [rcx+10h]
0x18000e9f2  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000e9f9  call    WPP_SF_d
0x18000e9fe  jmp     loc_18000E8A0
```
