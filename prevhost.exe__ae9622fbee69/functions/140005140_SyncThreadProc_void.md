# SyncThreadProc(void *)

- ea: `0x140005140`
- end: `0x140005222`
- name: `?SyncThreadProc@@YAKPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001470`
- `0x140004458`
- `0x140005140`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000519c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000519c`

## pseudocode

```c
__int64 __fastcall SyncThreadProc(_DWORD *lpThreadParameter)
{
  IID v2; // xmm0
  HRESULT v3; // eax
  int v4; // edi
  LPVOID v5; // rsi
  int v6; // eax
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 8LL))(lpThreadParameter);
  v2 = *(IID *)(lpThreadParameter + 3);
  ppv = 0;
  rclsid = v2;
  v3 = CoCreateInstance(&rclsid, 0, 1u, &GUID_8895b1c6_b41f_4c1c_a562_0d564250836f, &ppv);
  v4 = v3;
  if ( !lpThreadParameter[14] )
  {
    if ( v3 >= 0 )
    {
      v5 = ppv;
      v6 = CMarshalInterfaceOnce<IUnknown>::Marshal(lpThreadParameter + 18, lpThreadParameter + 7, ppv);
      if ( v6 < 0 )
      {
        lpThreadParameter[15] = v6;
      }
      else
      {
        lpThreadParameter[15] = v4;
        *((_QWORD *)lpThreadParameter + 8) = v5;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
    else
    {
      lpThreadParameter[15] = v3;
    }
    lpThreadParameter[14] = 1;
  }
  if ( v4 >= 0 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x140005140  mov     [rsp+arg_8], rbx
0x140005145  mov     [rsp+arg_10], rsi
0x14000514a  push    rdi
0x14000514b  sub     rsp, 50h
0x14000514f  mov     rax, cs:__security_cookie
0x140005156  xor     rax, rsp
0x140005159  mov     [rsp+58h+var_10], rax
0x14000515e  mov     rax, [rcx]
0x140005161  mov     rbx, rcx
0x140005164  mov     rax, [rax+8]
0x140005168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000516d  movups  xmm0, xmmword ptr [rbx+0Ch]
0x140005171  xor     edx, edx; pUnkOuter
0x140005173  mov     [rsp+58h+var_28], 0
0x14000517c  lea     rax, [rsp+58h+var_28]
0x140005181  lea     r9, _GUID_8895b1c6_b41f_4c1c_a562_0d564250836f; riid
0x140005188  mov     [rsp+58h+ppv], rax; ppv
0x14000518d  lea     rcx, [rsp+58h+rclsid]; rclsid
0x140005192  lea     r8d, [rdx+1]; dwClsContext
0x140005196  movdqu  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x14000519c  call    cs:__imp_CoCreateInstance
0x1400051a2  cmp     dword ptr [rbx+38h], 0
0x1400051a6  mov     edi, eax
0x1400051a8  jnz     short loc_1400051EE
0x1400051aa  test    eax, eax
0x1400051ac  jns     short loc_1400051B3
0x1400051ae  mov     [rbx+3Ch], eax
0x1400051b1  jmp     short loc_1400051E7
0x1400051b3  mov     rsi, [rsp+58h+var_28]
0x1400051b8  lea     rdx, [rbx+1Ch]
0x1400051bc  mov     r8, rsi
0x1400051bf  lea     rcx, [rbx+48h]
0x1400051c3  call    ?Marshal@?$CMarshalInterfaceOnce@UIUnknown@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CMarshalInterfaceOnce<IUnknown>::Marshal(_GUID const &,IUnknown *)
0x1400051c8  test    eax, eax
0x1400051ca  js      short loc_1400051E4
0x1400051cc  mov     [rbx+3Ch], edi
0x1400051cf  mov     rcx, rsi
0x1400051d2  mov     [rbx+40h], rsi
0x1400051d6  mov     rax, [rsi]
0x1400051d9  mov     rax, [rax+8]
0x1400051dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051e2  jmp     short loc_1400051E7
0x1400051e4  mov     [rbx+3Ch], eax
0x1400051e7  mov     dword ptr [rbx+38h], 1
0x1400051ee  test    edi, edi
0x1400051f0  js      short loc_140005203
0x1400051f2  mov     rcx, [rsp+58h+var_28]
0x1400051f7  mov     rax, [rcx]
0x1400051fa  mov     rax, [rax+10h]
0x1400051fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005203  xor     eax, eax
0x140005205  mov     rcx, [rsp+58h+var_10]
0x14000520a  xor     rcx, rsp; StackCookie
0x14000520d  call    __security_check_cookie
0x140005212  mov     rbx, [rsp+58h+arg_8]
0x140005217  mov     rsi, [rsp+58h+arg_10]
0x14000521c  add     rsp, 50h
0x140005220  pop     rdi
0x140005221  retn
```
