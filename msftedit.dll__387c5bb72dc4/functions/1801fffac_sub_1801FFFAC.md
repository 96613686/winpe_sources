# sub_1801FFFAC

- ea: `0x1801fffac`
- end: `0x1802000f1`
- name: `sub_1801FFFAC`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801fd354`

## callees

- `0x1801fffac`
- `0x18027a010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1801fffc2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1801fffc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801ffff1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020001e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020004b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801ffff1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020001e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020004b`

## pseudocode

```c
__int64 __fastcall sub_1801FFFAC(__int64 a1)
{
  HRESULT Instance; // ebx
  _QWORD *v3; // rsi
  _QWORD *v4; // r14
  __int64 (__fastcall ***v5)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF

  Instance = 0;
  v3 = (_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 64) = RegisterWindowMessageW(L"RichEdit_TouchSelectionHandle_Animation");
  if ( !*v3 )
  {
    Instance = CoCreateInstance(&rclsid, 0, 1u, &stru_1802BF4A8, (LPVOID *)(a1 + 16));
    if ( Instance >= 0 )
    {
      v4 = (_QWORD *)(a1 + 24);
      Instance = CoCreateInstance(&stru_1802A80D0, 0, 1u, &stru_1802BF4B8, (LPVOID *)(a1 + 24));
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(&stru_1802A80C0, 0, 1u, &stru_1802BF498, (LPVOID *)(a1 + 32));
        if ( Instance >= 0 )
        {
          v5 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))*v3;
          v7 = 0;
          Instance = (**v5)(v5, qword_1802A8080, &v7);
          if ( Instance >= 0 )
          {
            if ( !v7
              || (Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v4 + 24LL))(*v4, v7, 1),
                  Instance >= 0) )
            {
              Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 32LL))(*v4, a1);
              if ( Instance >= 0 )
                return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v3 + 136LL))(
                                       *v3,
                                       (a1 + 8) & -(__int64)(a1 != 0),
                                       0);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801fffac  push    rbx
0x1801fffae  push    rsi
0x1801fffaf  push    rdi
0x1801fffb0  push    r14
0x1801fffb2  sub     rsp, 38h
0x1801fffb6  mov     rdi, rcx
0x1801fffb9  xor     ebx, ebx
0x1801fffbb  lea     rcx, aRicheditTouchs; "RichEdit_TouchSelectionHandle_Animation"
0x1801fffc2  call    cs:RegisterWindowMessageW
0x1801fffc8  lea     rsi, [rdi+10h]
0x1801fffcc  mov     [rdi+40h], eax
0x1801fffcf  cmp     [rsi], rbx
0x1801fffd2  jnz     loc_1802000E5
0x1801fffd8  lea     r9, stru_1802BF4A8; riid
0x1801fffdf  mov     [rsp+58h+ppv], rsi; ppv
0x1801fffe4  xor     edx, edx; pUnkOuter
0x1801fffe6  lea     r8d, [rbx+1]; dwClsContext
0x1801fffea  lea     rcx, rclsid; rclsid
0x1801ffff1  call    cs:CoCreateInstance
0x1801ffff7  mov     ebx, eax
0x1801ffff9  test    eax, eax
0x1801ffffb  js      loc_1802000E5
0x180200001  xor     edx, edx; pUnkOuter
0x180200003  lea     r14, [rdi+18h]
0x180200007  lea     r9, stru_1802BF4B8; riid
0x18020000e  mov     [rsp+58h+ppv], r14; ppv
0x180200013  lea     rcx, stru_1802A80D0; rclsid
0x18020001a  lea     r8d, [rdx+1]; dwClsContext
0x18020001e  call    cs:CoCreateInstance
0x180200024  mov     ebx, eax
0x180200026  test    eax, eax
0x180200028  js      loc_1802000E5
0x18020002e  xor     edx, edx; pUnkOuter
0x180200030  lea     rax, [rdi+20h]
0x180200034  lea     r9, stru_1802BF498; riid
0x18020003b  mov     [rsp+58h+ppv], rax; ppv
0x180200040  lea     rcx, stru_1802A80C0; rclsid
0x180200047  lea     r8d, [rdx+1]; dwClsContext
0x18020004b  call    cs:CoCreateInstance
0x180200051  mov     ebx, eax
0x180200053  test    eax, eax
0x180200055  js      loc_1802000E5
0x18020005b  mov     rcx, [rsi]
0x18020005e  lea     r8, [rsp+58h+arg_0]
0x180200063  mov     [rsp+58h+arg_0], 0
0x18020006c  lea     rdx, qword_1802A8080
0x180200073  mov     rax, [rcx]
0x180200076  mov     rax, [rax]
0x180200079  call    j__guard_dispatch_icall
0x18020007e  mov     ebx, eax
0x180200080  test    eax, eax
0x180200082  js      short loc_1802000E5
0x180200084  mov     rdx, [rsp+58h+arg_0]
0x180200089  test    rdx, rdx
0x18020008c  jz      short loc_1802000A9
0x18020008e  mov     rcx, [r14]
0x180200091  mov     r8d, 1
0x180200097  mov     rax, [rcx]
0x18020009a  mov     rax, [rax+18h]
0x18020009e  call    j__guard_dispatch_icall
0x1802000a3  mov     ebx, eax
0x1802000a5  test    eax, eax
0x1802000a7  js      short loc_1802000E5
0x1802000a9  mov     rcx, [r14]
0x1802000ac  mov     rdx, rdi
0x1802000af  mov     rax, [rcx]
0x1802000b2  mov     rax, [rax+20h]
0x1802000b6  call    j__guard_dispatch_icall
0x1802000bb  mov     ebx, eax
0x1802000bd  test    eax, eax
0x1802000bf  js      short loc_1802000E5
0x1802000c1  mov     rcx, [rsi]
0x1802000c4  lea     rax, [rdi+8]
0x1802000c8  neg     rdi
0x1802000cb  sbb     rdx, rdx
0x1802000ce  xor     r8d, r8d
0x1802000d1  mov     r9, [rcx]
0x1802000d4  and     rdx, rax
0x1802000d7  mov     rax, [r9+88h]
0x1802000de  call    j__guard_dispatch_icall
0x1802000e3  mov     ebx, eax
0x1802000e5  mov     eax, ebx
0x1802000e7  add     rsp, 38h
0x1802000eb  pop     r14
0x1802000ed  pop     rdi
0x1802000ee  pop     rsi
0x1802000ef  pop     rbx
0x1802000f0  retn
```
