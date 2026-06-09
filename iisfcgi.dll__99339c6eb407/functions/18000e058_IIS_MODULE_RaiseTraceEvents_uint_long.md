# IIS_MODULE::RaiseTraceEvents(uint,long)

- ea: `0x18000e058`
- end: `0x18000e30e`
- name: `?RaiseTraceEvents@IIS_MODULE@@AEAAXIJ@Z`
- size: `694`
- prototype: `void __fastcall(IIS_MODULE *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb5c`

## callees

- `0x18000e058`
- `0x180010010`

## string_xrefs

- `0x18000e285`: `FASTCGI_PATH_NOT_FOUND`

## pseudocode

```c
void __fastcall IIS_MODULE::RaiseTraceEvents(IIS_MODULE *this, int a2, int a3)
{
  int (__fastcall ***v5)(_QWORD, GUID **); // rdi
  int (__fastcall **v6)(_QWORD, GUID **); // rcx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  const wchar_t *v15; // rax
  int (__fastcall **v16)(_QWORD, GUID **); // rax
  int (__fastcall *v17)(_QWORD, GUID **); // rax
  GUID *v18; // [rsp+20h] [rbp-69h] BYREF
  __int64 v19; // [rsp+28h] [rbp-61h]
  GUID *v20; // [rsp+30h] [rbp-59h]
  __int64 v21; // [rsp+38h] [rbp-51h]
  const wchar_t *v22; // [rsp+40h] [rbp-49h]
  int v23; // [rsp+48h] [rbp-41h]
  int v24; // [rsp+4Ch] [rbp-3Dh]
  __int128 v25; // [rsp+50h] [rbp-39h]
  int v26; // [rsp+60h] [rbp-29h]
  int v27; // [rsp+64h] [rbp-25h]
  __int64 v28; // [rsp+68h] [rbp-21h]
  GUID **v29; // [rsp+70h] [rbp-19h]
  GUID *v30; // [rsp+80h] [rbp-9h] BYREF
  __int128 v31; // [rsp+88h] [rbp-1h]
  int v32; // [rsp+98h] [rbp+Fh]
  __int64 v33; // [rsp+A0h] [rbp+17h]
  const wchar_t *v34; // [rsp+A8h] [rbp+1Fh]
  int v35; // [rsp+B0h] [rbp+27h]
  int *v36; // [rsp+B8h] [rbp+2Fh]
  int v37; // [rsp+C0h] [rbp+37h]
  __int64 v38; // [rsp+C8h] [rbp+3Fh]
  int v39; // [rsp+F0h] [rbp+67h] BYREF

  v5 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 272LL))(*((_QWORD *)this + 21));
  v30 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v6 = *v5;
  v31 = 0;
  if ( (*v6)(v5, &v30) >= 0 && DWORD2(v31) && DWORD1(v31) >= 2 && ((_DWORD)v31 == 4096 || (v31 & 0x1000) != 0) )
  {
    v7 = a2 - 200000;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 2;
            if ( !v11 )
            {
              v39 = a3;
              v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
              v22 = L"FASTCGI_UNKNOWN_ERROR";
              v23 = 1;
              v27 = 1;
              v30 = (GUID *)L"ContextId";
              v34 = L"ErrorCode";
              v36 = &v39;
              v19 = 4096;
              v21 = 10;
              v28 = 2;
              v35 = 19;
              v37 = 4;
              v38 = 0;
LABEL_26:
              v29 = &v30;
              v16 = *v5;
              v26 = 0;
              *((_QWORD *)&v31 + 1) = 0;
              v33 = 0;
              v17 = v16[2];
              v18 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
              v24 = 2;
              v25 = 0;
              LODWORD(v31) = 72;
              v32 = 16;
              v17(v5, &v18);
              return;
            }
            v12 = v11 - 1;
            if ( !v12 )
            {
              v19 = 4096;
              v21 = 1;
              v22 = L"FASTCGI_ACTIVITY_TIMEOUT";
              v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
LABEL_25:
              v28 = 1;
              v23 = 1;
              v27 = 1;
              v30 = (GUID *)L"ContextId";
              goto LABEL_26;
            }
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                if ( v14 != 1 )
                  return;
                v21 = 4;
                v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
                v15 = L"FASTCGI_RAPID_FAILURE_PROTECTION";
              }
              else
              {
                v21 = 8;
                v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
                v15 = L"FASTCGI_APPLICATION_MANAGER_SHUTDOWN";
              }
            }
            else
            {
              v21 = 2;
              v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
              v15 = L"FASTCGI_REQUEST_TIMEOUT";
            }
          }
          else
          {
            v21 = 3;
            v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
            v15 = L"FASTCGI_UNEXPECTED_EXIT";
          }
        }
        else
        {
          v21 = 7;
          v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
          v15 = L"FASTCGI_ADD_JOBOBJECT_FAIL";
        }
      }
      else
      {
        v21 = 9;
        v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
        v15 = L"FASTCGI_QUEUE_FULL";
      }
    }
    else
    {
      v21 = 5;
      v20 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
      v15 = L"FASTCGI_PATH_NOT_FOUND";
    }
    v19 = 4096;
    v22 = v15;
    goto LABEL_25;
  }
}

```

## disassembly

```asm
0x18000e058  mov     [rsp-8+arg_8], rbx
0x18000e05d  mov     [rsp-8+arg_10], rsi
0x18000e062  push    rbp
0x18000e063  push    rdi
0x18000e064  push    r14
0x18000e066  lea     rbp, [rsp-47h]
0x18000e06b  sub     rsp, 0D0h
0x18000e072  mov     rcx, [rcx+0A8h]
0x18000e079  mov     esi, r8d
0x18000e07c  mov     ebx, edx
0x18000e07e  mov     rax, [rcx]
0x18000e081  mov     rax, [rax+110h]
0x18000e088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e08d  mov     rdi, rax
0x18000e090  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000e097  xorps   xmm0, xmm0
0x18000e09a  mov     [rbp+57h+var_60], r14
0x18000e09e  lea     rdx, [rbp+57h+var_60]
0x18000e0a2  mov     rcx, [rax]
0x18000e0a5  movdqu  [rbp+57h+var_58], xmm0
0x18000e0aa  mov     rax, [rcx]
0x18000e0ad  mov     rcx, rdi
0x18000e0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b5  xor     edx, edx
0x18000e0b7  test    eax, eax
0x18000e0b9  js      loc_18000E2F6
0x18000e0bf  cmp     dword ptr [rbp+57h+var_58+8], edx
0x18000e0c2  jz      loc_18000E2F6
0x18000e0c8  lea     r8d, [rdx+2]
0x18000e0cc  cmp     dword ptr [rbp+57h+var_58+4], r8d
0x18000e0d0  jb      loc_18000E2F6
0x18000e0d6  mov     ecx, 1000h
0x18000e0db  cmp     dword ptr [rbp+57h+var_58], ecx
0x18000e0de  jz      short loc_18000E0E9
0x18000e0e0  test    dword ptr [rbp+57h+var_58], ecx
0x18000e0e3  jz      loc_18000E2F6
0x18000e0e9  sub     ebx, 30D40h
0x18000e0ef  jz      loc_18000E272
0x18000e0f5  sub     ebx, 1
0x18000e0f8  jz      loc_18000E256
0x18000e0fe  sub     ebx, 1
0x18000e101  jz      loc_18000E23A
0x18000e107  sub     ebx, 1
0x18000e10a  jz      loc_18000E21E
0x18000e110  sub     ebx, r8d
0x18000e113  jz      loc_18000E1B1
0x18000e119  sub     ebx, 1
0x18000e11c  jz      short loc_18000E18A
0x18000e11e  sub     ebx, 1
0x18000e121  jz      short loc_18000E16F
0x18000e123  sub     ebx, 1
0x18000e126  jz      short loc_18000E150
0x18000e128  cmp     ebx, 1
0x18000e12b  jnz     loc_18000E2F6
0x18000e131  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e138  mov     [rbp+57h+var_A8], 4
0x18000e140  mov     [rbp+57h+var_B0], rax
0x18000e144  lea     rax, aFastcgiRapidFa; "FASTCGI_RAPID_FAILURE_PROTECTION"
0x18000e14b  jmp     loc_18000E28C
0x18000e150  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e157  mov     [rbp+57h+var_A8], 8
0x18000e15f  mov     [rbp+57h+var_B0], rax
0x18000e163  lea     rax, aFastcgiApplica; "FASTCGI_APPLICATION_MANAGER_SHUTDOWN"
0x18000e16a  jmp     loc_18000E28C
0x18000e16f  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e176  mov     [rbp+57h+var_A8], r8
0x18000e17a  mov     [rbp+57h+var_B0], rax
0x18000e17e  lea     rax, aFastcgiRequest; "FASTCGI_REQUEST_TIMEOUT"
0x18000e185  jmp     loc_18000E28C
0x18000e18a  mov     [rbp+57h+var_B8], rcx
0x18000e18e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e195  lea     rcx, aFastcgiActivit; "FASTCGI_ACTIVITY_TIMEOUT"
0x18000e19c  mov     [rbp+57h+var_A8], 1
0x18000e1a4  mov     [rbp+57h+var_A0], rcx
0x18000e1a8  mov     [rbp+57h+var_B0], rax
0x18000e1ac  jmp     loc_18000E294
0x18000e1b1  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e1b8  mov     [rbp+57h+arg_0], esi
0x18000e1bb  mov     [rbp+57h+var_B0], rax
0x18000e1bf  lea     rax, aFastcgiUnknown; "FASTCGI_UNKNOWN_ERROR"
0x18000e1c6  mov     [rbp+57h+var_A0], rax
0x18000e1ca  mov     eax, 1
0x18000e1cf  mov     [rbp+57h+var_98], eax
0x18000e1d2  mov     [rbp+57h+var_7C], eax
0x18000e1d5  lea     rax, aContextid; "ContextId"
0x18000e1dc  mov     [rbp+57h+var_60], rax
0x18000e1e0  lea     rax, aErrorcode; "ErrorCode"
0x18000e1e7  mov     [rbp+57h+var_38], rax
0x18000e1eb  lea     rax, [rbp+57h+arg_0]
0x18000e1ef  mov     [rbp+57h+var_28], rax
0x18000e1f3  lea     rax, [rbp+57h+var_60]
0x18000e1f7  mov     [rbp+57h+var_B8], rcx
0x18000e1fb  mov     [rbp+57h+var_A8], 0Ah
0x18000e203  mov     [rbp+57h+var_78], r8
0x18000e207  mov     [rbp+57h+var_30], 13h
0x18000e20e  mov     [rbp+57h+var_20], 4
0x18000e215  mov     [rbp+57h+var_18], rdx
0x18000e219  jmp     loc_18000E2B6
0x18000e21e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e225  mov     [rbp+57h+var_A8], 3
0x18000e22d  mov     [rbp+57h+var_B0], rax
0x18000e231  lea     rax, aFastcgiUnexpec; "FASTCGI_UNEXPECTED_EXIT"
0x18000e238  jmp     short loc_18000E28C
0x18000e23a  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e241  mov     [rbp+57h+var_A8], 7
0x18000e249  mov     [rbp+57h+var_B0], rax
0x18000e24d  lea     rax, aFastcgiAddJobo; "FASTCGI_ADD_JOBOBJECT_FAIL"
0x18000e254  jmp     short loc_18000E28C
0x18000e256  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e25d  mov     [rbp+57h+var_A8], 9
0x18000e265  mov     [rbp+57h+var_B0], rax
0x18000e269  lea     rax, aFastcgiQueueFu; "FASTCGI_QUEUE_FULL"
0x18000e270  jmp     short loc_18000E28C
0x18000e272  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000e279  mov     [rbp+57h+var_A8], 5
0x18000e281  mov     [rbp+57h+var_B0], rax
0x18000e285  lea     rax, aFastcgiPathNot; "FASTCGI_PATH_NOT_FOUND"
0x18000e28c  mov     [rbp+57h+var_B8], rcx
0x18000e290  mov     [rbp+57h+var_A0], rax
0x18000e294  mov     eax, 1
0x18000e299  mov     [rbp+57h+var_78], 1
0x18000e2a1  mov     [rbp+57h+var_98], eax
0x18000e2a4  mov     [rbp+57h+var_7C], eax
0x18000e2a7  lea     rax, aContextid; "ContextId"
0x18000e2ae  mov     [rbp+57h+var_60], rax
0x18000e2b2  lea     rax, [rbp+57h+var_60]
0x18000e2b6  mov     [rbp+57h+var_70], rax
0x18000e2ba  xorps   xmm0, xmm0
0x18000e2bd  mov     rax, [rdi]
0x18000e2c0  mov     rcx, rdi
0x18000e2c3  mov     [rbp+57h+var_80], edx
0x18000e2c6  mov     qword ptr [rbp+57h+var_58+8], rdx
0x18000e2ca  mov     [rbp+57h+var_40], rdx
0x18000e2ce  lea     rdx, [rbp+57h+var_C0]
0x18000e2d2  mov     rax, [rax+10h]
0x18000e2d6  mov     [rbp+57h+var_C0], r14
0x18000e2da  mov     [rbp+57h+var_94], r8d
0x18000e2de  movdqa  [rbp+57h+var_90], xmm0
0x18000e2e3  mov     dword ptr [rbp+57h+var_58], 48h ; 'H'
0x18000e2ea  mov     [rbp+57h+var_48], 10h
0x18000e2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2f6  lea     r11, [rsp+0E0h+var_10]
0x18000e2fe  mov     rbx, [r11+28h]
0x18000e302  mov     rsi, [r11+30h]
0x18000e306  mov     rsp, r11
0x18000e309  pop     r14
0x18000e30b  pop     rdi
0x18000e30c  pop     rbp
0x18000e30d  retn
```
