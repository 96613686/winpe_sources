# UpdateSharedAccessServicePerSettings(IWbemServices *,ushort *,_GUID,bool)

- ea: `0x18002ad0c`
- end: `0x18002ae26`
- name: `?UpdateSharedAccessServicePerSettings@@YAJPEAUIWbemServices@@PEAGU_GUID@@_N@Z`
- size: `282`
- prototype: `int(struct IWbemServices *, unsigned __int16 *, struct _GUID *__struct_ptr, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800275a0`
- `0x180027860`

## callees

- `0x18000ab70`
- `0x18002ad0c`
- `0x18002ae2c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ad37`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ad37`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad86`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad86`

## pseudocode

```c
__int64 __fastcall UpdateSharedAccessServicePerSettings(
        struct IWbemServices *a1,
        unsigned __int16 *a2,
        struct _GUID *a3,
        bool a4)
{
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  struct IWbemServicesVtbl *lpVtbl; // r9
  int v11; // ebx
  int v13; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+48h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID v16; // [rsp+60h] [rbp-18h] BYREF

  v14 = 0;
  v8 = SysAllocString(L"SELECT * FROM HNet_ConnectionProperties WHERE IsIcsPublic != FALSE or IsIcsPrivate != FALSE");
  v9 = v8;
  if ( v8 )
  {
    lpVtbl = a1->lpVtbl;
    v14 = 0;
    v11 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, BSTR, __int64, _QWORD, __int64 *))lpVtbl->ExecQuery)(
            a1,
            a2,
            v8,
            48,
            0,
            &v14);
    SysFreeString(v9);
    if ( !v11 )
    {
      v13 = 0;
      v15 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v14 + 32LL))(
              v14,
              0xFFFFFFFFLL,
              1,
              &v15,
              &v13);
      if ( v11 >= 0 )
      {
        if ( v13 == 1 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v16 = *a3;
          UpdateSharingSettingsFromStorage(&v16, a4);
        }
        else
        {
          HNetCfgStopSharing(0xFFFFFFFF, 0xFFFFFFFF);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002ad0c  push    rbp
0x18002ad0e  push    rbx
0x18002ad0f  push    rsi
0x18002ad10  push    rdi
0x18002ad11  push    r14
0x18002ad13  push    r15
0x18002ad15  mov     rbp, rsp
0x18002ad18  sub     rsp, 78h
0x18002ad1c  mov     rbx, rcx
0x18002ad1f  mov     [rbp+var_30], 0
0x18002ad27  lea     rcx, ?c_wszServiceCheckQuery@@3QBGB; "SELECT * FROM HNet_ConnectionProperties"...
0x18002ad2e  mov     sil, r9b
0x18002ad31  mov     r14, r8
0x18002ad34  mov     r15, rdx
0x18002ad37  call    cs:__imp_SysAllocString
0x18002ad3d  mov     rdi, rax
0x18002ad40  test    rax, rax
0x18002ad43  jz      loc_18002AE12
0x18002ad49  mov     r9, [rbx]
0x18002ad4c  lea     rcx, [rbp+var_30]
0x18002ad50  mov     [rsp+78h+var_50], rcx
0x18002ad55  mov     r8, rdi
0x18002ad58  mov     rdx, r15
0x18002ad5b  mov     [rbp+var_30], 0
0x18002ad63  mov     rcx, rbx
0x18002ad66  mov     [rsp+78h+var_58], 0
0x18002ad6f  mov     rax, [r9+0A0h]
0x18002ad76  mov     r9d, 30h ; '0'
0x18002ad7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad81  mov     rcx, rdi; bstrString
0x18002ad84  mov     ebx, eax
0x18002ad86  call    cs:__imp_SysFreeString
0x18002ad8c  test    ebx, ebx
0x18002ad8e  jnz     loc_18002AE17
0x18002ad94  mov     rcx, [rbp+var_30]
0x18002ad98  lea     rdx, [rbp+var_38]
0x18002ad9c  mov     [rbp+var_38], ebx
0x18002ad9f  lea     r9, [rbp+var_28]
0x18002ada3  mov     [rbp+var_28], 0
0x18002adab  lea     r8d, [rbx+1]
0x18002adaf  mov     [rsp+78h+var_58], rdx
0x18002adb4  or      edx, 0FFFFFFFFh
0x18002adb7  mov     rax, [rcx]
0x18002adba  mov     rax, [rax+20h]
0x18002adbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adc3  mov     ebx, eax
0x18002adc5  test    eax, eax
0x18002adc7  js      short loc_18002AE00
0x18002adc9  cmp     [rbp+var_38], 1
0x18002adcd  jnz     short loc_18002ADF6
0x18002adcf  mov     rcx, [rbp+var_28]
0x18002add3  mov     rdx, [rcx]
0x18002add6  mov     rax, [rdx+10h]
0x18002adda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002addf  movaps  xmm0, xmmword ptr [r14]
0x18002ade3  lea     rcx, [rbp+var_18]; struct _GUID
0x18002ade7  mov     dl, sil; bool
0x18002adea  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x18002adef  call    ?UpdateSharingSettingsFromStorage@@YAKU_GUID@@_N@Z; UpdateSharingSettingsFromStorage(_GUID,bool)
0x18002adf4  jmp     short loc_18002AE00
0x18002adf6  or      ecx, 0FFFFFFFFh; unsigned int
0x18002adf9  mov     edx, ecx; unsigned int
0x18002adfb  call    HNetCfgStopSharing
0x18002ae00  mov     rcx, [rbp+var_30]
0x18002ae04  mov     rax, [rcx]
0x18002ae07  mov     rax, [rax+10h]
0x18002ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae10  jmp     short loc_18002AE17
0x18002ae12  mov     ebx, 8007000Eh
0x18002ae17  mov     eax, ebx
0x18002ae19  add     rsp, 78h
0x18002ae1d  pop     r15
0x18002ae1f  pop     r14
0x18002ae21  pop     rdi
0x18002ae22  pop     rsi
0x18002ae23  pop     rbx
0x18002ae24  pop     rbp
0x18002ae25  retn
```
