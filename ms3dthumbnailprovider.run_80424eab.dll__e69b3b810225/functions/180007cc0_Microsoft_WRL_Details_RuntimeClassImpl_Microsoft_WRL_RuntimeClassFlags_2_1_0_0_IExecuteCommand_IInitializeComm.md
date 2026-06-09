# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007cc0`
- end: `0x180007db9`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007dc0`
- `0x180007dd0`

## callees

- `0x180007cc0`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // ebx

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 2140243376
      && a2[1] == *(_DWORD *)&GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data2
      && a2[2] == *(_DWORD *)GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4
      && a2[3] == *(_DWORD *)&GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4[4] )
    {
      goto LABEL_10;
    }
    goto LABEL_11;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
LABEL_11:
    a1 += 8;
    if ( *a2 != -2063115569 )
    {
      if ( *a2 == 480040379
        && a2[1] == *(_DWORD *)&GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data2
        && a2[2] == *(_DWORD *)GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4
        && a2[3] == *(_DWORD *)&GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4[4] )
      {
        *a3 = a1 + 8;
        v3 = 0;
LABEL_16:
        if ( v3 < 0 )
          return (unsigned int)v3;
LABEL_17:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        return (unsigned int)v3;
      }
LABEL_15:
      v3 = -2147467262;
      goto LABEL_16;
    }
    if ( a2[1] != *(_DWORD *)&GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data2
      || a2[2] != *(_DWORD *)GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data4
      || a2[3] != *(_DWORD *)&GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data4[4] )
    {
      goto LABEL_15;
    }
LABEL_10:
    *a3 = a1;
    v3 = 0;
    goto LABEL_17;
  }
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180007cc0  push    rbx
0x180007cc2  sub     rsp, 20h
0x180007cc6  mov     qword ptr [r8], 0
0x180007ccd  cmp     dword ptr [rdx], 0
0x180007cd0  jnz     short loc_180007D06
0x180007cd2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180007cd8  cmp     [rdx+4], eax
0x180007cdb  jnz     short loc_180007D36
0x180007cdd  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180007ce3  cmp     [rdx+8], eax
0x180007ce6  jnz     short loc_180007D36
0x180007ce8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180007cee  cmp     [rdx+0Ch], eax
0x180007cf1  jnz     short loc_180007D36
0x180007cf3  mov     [r8], rcx
0x180007cf6  mov     rax, [rcx]
0x180007cf9  mov     rax, [rax+8]
0x180007cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d02  xor     ebx, ebx
0x180007d04  jmp     short loc_180007D7C
0x180007d06  cmp     dword ptr [rdx], 7F9185B0h
0x180007d0c  jnz     short loc_180007D36
0x180007d0e  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data2
0x180007d14  cmp     [rdx+4], eax
0x180007d17  jnz     short loc_180007D36
0x180007d19  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4
0x180007d1f  cmp     [rdx+8], eax
0x180007d22  jnz     short loc_180007D36
0x180007d24  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4+4
0x180007d2a  cmp     [rdx+0Ch], eax
0x180007d2d  jnz     short loc_180007D36
0x180007d2f  mov     [r8], rcx
0x180007d32  xor     ebx, ebx
0x180007d34  jmp     short loc_180007D6C
0x180007d36  add     rcx, 8
0x180007d3a  cmp     dword ptr [rdx], 85075ACFh
0x180007d40  jnz     short loc_180007D84
0x180007d42  mov     eax, dword ptr cs:_GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data2
0x180007d48  cmp     [rdx+4], eax
0x180007d4b  jnz     short loc_180007D63
0x180007d4d  mov     eax, dword ptr cs:_GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data4
0x180007d53  cmp     [rdx+8], eax
0x180007d56  jnz     short loc_180007D63
0x180007d58  mov     eax, dword ptr cs:_GUID_85075acf_231f_40ea_9610_d26b7b58f638.Data4+4
0x180007d5e  cmp     [rdx+0Ch], eax
0x180007d61  jz      short loc_180007D2F
0x180007d63  mov     ebx, 80004002h
0x180007d68  test    ebx, ebx
0x180007d6a  js      short loc_180007D7C
0x180007d6c  mov     rcx, [r8]
0x180007d6f  mov     rdx, [rcx]
0x180007d72  mov     rax, [rdx+8]
0x180007d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7b  nop
0x180007d7c  mov     eax, ebx
0x180007d7e  add     rsp, 20h
0x180007d82  pop     rbx
0x180007d83  retn
0x180007d84  cmp     dword ptr [rdx], 1C9CD5BBh
0x180007d8a  jnz     short loc_180007D63
0x180007d8c  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data2
0x180007d92  cmp     [rdx+4], eax
0x180007d95  jnz     short loc_180007D63
0x180007d97  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4
0x180007d9d  cmp     [rdx+8], eax
0x180007da0  jnz     short loc_180007D63
0x180007da2  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4+4
0x180007da8  cmp     [rdx+0Ch], eax
0x180007dab  jnz     short loc_180007D63
0x180007dad  lea     rax, [rcx+8]
0x180007db1  mov     [r8], rax
0x180007db4  xor     ebx, ebx
0x180007db6  jmp     short loc_180007D68
```
