# DacClientCallbackThreadProc(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180002840`
- end: `0x180002a4e`
- name: `?DacClientCallbackThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `526`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002730`

## callees

- `0x180002840`
- `0x180002a54`
- `0x180002ca4`
- `0x180002e88`
- `0x180002f10`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000294d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000294d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180002896`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180002896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002971`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a16`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a16`

## pseudocode

```c
void __fastcall DacClientCallbackThreadProc(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context)
{
  __int64 v2; // rsi
  HMODULE v5; // rbp
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rcx
  signed int LastError; // eax

  v2 = Context[3];
  v5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  if ( *(_DWORD *)(v2 + 80) )
  {
    if ( Instance )
      CallbackMayRunLong(Instance);
    v6 = *((_DWORD *)Context + 28);
    if ( v6 <= 5 )
    {
      if ( v6 == 5 )
        goto LABEL_29;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( (unsigned int)(v8 - 1) <= 1 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))Context[15])(
                *((unsigned int *)Context + 36),
                Context[16],
                *((unsigned int *)Context + 34));
            goto LABEL_30;
          }
LABEL_29:
          ((void (__fastcall *)(_QWORD, _QWORD))Context[15])(Context[16], *((unsigned int *)Context + 34));
          goto LABEL_30;
        }
      }
      v9 = Context[18];
      v10 = *((unsigned int *)Context + 38);
LABEL_15:
      ((void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))Context[15])(
        v10,
        v9,
        Context[16],
        *((unsigned int *)Context + 34));
      goto LABEL_30;
    }
    v11 = v6 - 6;
    if ( !v11 )
      goto LABEL_29;
    v12 = v11 - 1;
    if ( !v12 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))Context[15])(
        Context[18],
        Context[16],
        *((unsigned int *)Context + 34));
      goto LABEL_30;
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
        v9 = Context[19];
        v10 = *((unsigned int *)Context + 36);
        goto LABEL_15;
      }
      if ( v14 != 1 )
        goto LABEL_30;
    }
    v15 = Context[16];
    *(_DWORD *)(v15 + 8) = *((_DWORD *)Context + 34);
    if ( !SetEvent(*(HANDLE *)v15)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids,
        (unsigned int)LastError);
    }
  }
LABEL_30:
  if ( *(_QWORD *)(v2 + 88) )
  {
    v5 = *(HMODULE *)(v2 + 88);
    *(_QWORD *)(v2 + 88) = 0;
  }
  FreeAsyncUserContext((struct _DAC_ASYNC_USER_CONTEXT *)Context);
  ReleaseClientContext((struct _DAC_CLIENT_CONTEXT *)v2);
  if ( v5 )
    FreeLibrary(v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
}

```

## disassembly

```asm
0x180002840  push    rbx
0x180002842  push    rbp
0x180002843  push    rsi
0x180002844  push    rdi
0x180002845  push    r14
0x180002847  sub     rsp, 30h
0x18000284b  mov     rsi, [rdx+18h]
0x18000284f  mov     rbx, rdx
0x180002852  mov     rdi, rcx
0x180002855  xor     ebp, ebp
0x180002857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000285e  lea     r14, WPP_GLOBAL_Control
0x180002865  cmp     rcx, r14
0x180002868  jz      short loc_180002883
0x18000286a  cmp     byte ptr [rcx+19h], 4
0x18000286e  jb      short loc_180002883
0x180002870  mov     rcx, [rcx+10h]
0x180002874  lea     edx, [rbp+0Ch]
0x180002877  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x18000287e  call    WPP_SF_s
0x180002883  mov     eax, [rsi+50h]
0x180002886  test    eax, eax
0x180002888  jz      loc_1800029EC
0x18000288e  test    rdi, rdi
0x180002891  jz      short loc_18000289C
0x180002893  mov     rcx, rdi; pci
0x180002896  call    cs:__imp_CallbackMayRunLong
0x18000289c  mov     ecx, [rbx+70h]
0x18000289f  cmp     ecx, 5
0x1800028a2  jg      short loc_180002915
0x1800028a4  jz      loc_1800029D6
0x1800028aa  test    ecx, ecx
0x1800028ac  jz      short loc_1800028EC
0x1800028ae  sub     ecx, 1
0x1800028b1  jz      short loc_1800028EC
0x1800028b3  sub     ecx, 1
0x1800028b6  jz      loc_1800029D6
0x1800028bc  sub     ecx, 1
0x1800028bf  jz      short loc_1800028CA
0x1800028c1  cmp     ecx, 1
0x1800028c4  jnz     loc_1800029EC
0x1800028ca  mov     r8d, [rbx+88h]
0x1800028d1  mov     rdx, [rbx+80h]
0x1800028d8  mov     ecx, [rbx+90h]
0x1800028de  mov     rax, [rbx+78h]
0x1800028e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e7  jmp     loc_1800029EC
0x1800028ec  mov     rdx, [rbx+90h]
0x1800028f3  mov     ecx, [rbx+98h]
0x1800028f9  mov     r8, [rbx+80h]
0x180002900  mov     r9d, [rbx+88h]
0x180002907  mov     rax, [rbx+78h]
0x18000290b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002910  jmp     loc_1800029EC
0x180002915  sub     ecx, 6
0x180002918  jz      loc_1800029D6
0x18000291e  sub     ecx, 1
0x180002921  jz      loc_1800029B6
0x180002927  sub     ecx, 1
0x18000292a  jz      short loc_18000293A
0x18000292c  sub     ecx, 1
0x18000292f  jz      short loc_1800029A4
0x180002931  cmp     ecx, 1
0x180002934  jnz     loc_1800029EC
0x18000293a  mov     rcx, [rbx+80h]
0x180002941  mov     eax, [rbx+88h]
0x180002947  mov     [rcx+8], eax
0x18000294a  mov     rcx, [rcx]; hEvent
0x18000294d  call    cs:__imp_SetEvent
0x180002953  test    eax, eax
0x180002955  jnz     loc_1800029EC
0x18000295b  mov     rax, cs:WPP_GLOBAL_Control
0x180002962  cmp     rax, r14
0x180002965  jz      loc_1800029EC
0x18000296b  cmp     byte ptr [rax+19h], 2
0x18000296f  jb      short loc_1800029EC
0x180002971  call    cs:__imp_GetLastError
0x180002977  test    eax, eax
0x180002979  jle     short loc_180002983
0x18000297b  movzx   eax, ax
0x18000297e  or      eax, 80070000h
0x180002983  mov     rcx, cs:WPP_GLOBAL_Control
0x18000298a  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002991  mov     edx, 0Dh
0x180002996  mov     r9d, eax
0x180002999  mov     rcx, [rcx+10h]
0x18000299d  call    WPP_SF_D
0x1800029a2  jmp     short loc_1800029EC
0x1800029a4  mov     rdx, [rbx+98h]
0x1800029ab  mov     ecx, [rbx+90h]
0x1800029b1  jmp     loc_1800028F9
0x1800029b6  mov     r8d, [rbx+88h]
0x1800029bd  mov     rdx, [rbx+80h]
0x1800029c4  mov     rcx, [rbx+90h]
0x1800029cb  mov     rax, [rbx+78h]
0x1800029cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d4  jmp     short loc_1800029EC
0x1800029d6  mov     edx, [rbx+88h]
0x1800029dc  mov     rcx, [rbx+80h]
0x1800029e3  mov     rax, [rbx+78h]
0x1800029e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ec  cmp     [rsi+58h], rbp
0x1800029f0  jz      short loc_1800029FE
0x1800029f2  mov     rbp, [rsi+58h]
0x1800029f6  mov     qword ptr [rsi+58h], 0
0x1800029fe  mov     rcx, rbx; struct _DAC_ASYNC_USER_CONTEXT *
0x180002a01  call    ?FreeAsyncUserContext@@YAXPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; FreeAsyncUserContext(_DAC_ASYNC_USER_CONTEXT *)
0x180002a06  mov     rcx, rsi; struct _DAC_CLIENT_CONTEXT *
0x180002a09  call    ?ReleaseClientContext@@YAKPEAU_DAC_CLIENT_CONTEXT@@@Z; ReleaseClientContext(_DAC_CLIENT_CONTEXT *)
0x180002a0e  test    rbp, rbp
0x180002a11  jz      short loc_180002A1C
0x180002a13  mov     rcx, rbp; hLibModule
0x180002a16  call    cs:__imp_FreeLibrary
0x180002a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a23  cmp     rcx, r14
0x180002a26  jz      short loc_180002A43
0x180002a28  cmp     byte ptr [rcx+19h], 4
0x180002a2c  jb      short loc_180002A43
0x180002a2e  mov     rcx, [rcx+10h]
0x180002a32  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002a39  mov     edx, 0Eh
0x180002a3e  call    WPP_SF_s
0x180002a43  add     rsp, 30h
0x180002a47  pop     r14
0x180002a49  pop     rdi
0x180002a4a  pop     rsi
0x180002a4b  pop     rbp
0x180002a4c  pop     rbx
0x180002a4d  retn
```
