# FixupDosDeviceDefinition(_LCMINIPORT *)

- ea: `0x1800e0fbc`
- end: `0x1800e111d`
- name: `?FixupDosDeviceDefinition@@YAHPEAU_LCMINIPORT@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct _LCMINIPORT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800deab0`

## callees

- `0x1800df488`
- `0x1800e045c`
- `0x1800e081c`
- `0x1800e0fbc`
- `0x1800e1338`
- `0x1800e13e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e10ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e10ac`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800e106a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800e106a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e1086`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e1086`
- `SPOOLSS!DllFreeSplStr` at `0x1800e10d5`
- `SPOOLSS!DllFreeSplStr` at `0x1800e10d5`
- `SPOOLSS!DllFreeSplMem` at `0x1800e10f5`
- `SPOOLSS!DllFreeSplMem` at `0x1800e10fe`
- `SPOOLSS!DllFreeSplMem` at `0x1800e10f5`
- `SPOOLSS!DllFreeSplMem` at `0x1800e10fe`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1001`
- `SPOOLSS!DllAllocSplMem` at `0x1800e104c`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1001`
- `SPOOLSS!DllAllocSplMem` at `0x1800e104c`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e1037`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e1037`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1077`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1093`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e10e2`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1077`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1093`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e10e2`
- `SPOOLSS!SplUnregisterForDeviceEvents` at `0x1800e10c3`
- `SPOOLSS!SplUnregisterForDeviceEvents` at `0x1800e10c3`

## pseudocode

```c
__int64 __fastcall FixupDosDeviceDefinition(struct _LCMINIPORT *a1)
{
  unsigned int v2; // edi
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // rbp
  HANDLE v5; // rsi
  WCHAR *v6; // rax
  const WCHAR *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rcx

  LocalMonTelemetry::WriteDbgTraceInfo("FixupDosDeviceDefinition", L"Port: %ws", *((_QWORD *)a1 + 3));
  if ( (*((_BYTE *)a1 + 44) & 2) == 0 || *((_QWORD *)a1 + 4) == -1 )
  {
    return (unsigned int)ValidateDosDevicePort(a1);
  }
  else
  {
    v2 = 0;
    v3 = (unsigned __int16 *)DllAllocSplMem(520);
    v4 = v3;
    if ( v3 )
    {
      if ( !StrNCatBuffW(v3, 0x104u, *((_QWORD *)a1 + 3), 0) )
      {
        LcmRemoveColon(v4);
        v5 = RevertToPrinterSelf();
        if ( v5 )
        {
          v6 = (WCHAR *)DllAllocSplMem(520);
          v7 = v6;
          if ( v6 )
          {
            if ( QueryDosDeviceW(v4, v6, 0x104u) )
            {
              if ( lstrcmpiW(v7, *((LPCWSTR *)a1 + 7)) )
              {
                RemoveDosDeviceDefinition(a1);
                CloseHandle(*((HANDLE *)a1 + 4));
                v8 = *((_QWORD *)a1 + 12);
                *((_QWORD *)a1 + 4) = -1;
                if ( v8 )
                {
                  SplUnregisterForDeviceEvents();
                  *((_QWORD *)a1 + 12) = 0;
                }
                v9 = *((_QWORD *)a1 + 7);
                *((_DWORD *)a1 + 11) &= 0xFFFFFFFC;
                DllFreeSplStr(v9);
                *((_QWORD *)a1 + 7) = 0;
                ImpersonatePrinterClient(v5);
                v2 = ValidateDosDevicePort(a1);
              }
              else
              {
                ImpersonatePrinterClient(v5);
                v2 = 1;
              }
            }
            else
            {
              ImpersonatePrinterClient(v5);
            }
            DllFreeSplMem(v7);
          }
        }
      }
      DllFreeSplMem(v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800e0fbc  push    rbx
0x1800e0fbe  push    rbp
0x1800e0fbf  push    rsi
0x1800e0fc0  push    rdi
0x1800e0fc1  push    r14
0x1800e0fc3  sub     rsp, 20h
0x1800e0fc7  mov     r8, [rcx+18h]
0x1800e0fcb  lea     rdx, aPortWs_0; "Port: %ws"
0x1800e0fd2  mov     rbx, rcx
0x1800e0fd5  lea     rcx, aFixupdosdevice; "FixupDosDeviceDefinition"
0x1800e0fdc  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e0fe1  test    byte ptr [rbx+2Ch], 2
0x1800e0fe5  jz      loc_1800E1106
0x1800e0feb  cmp     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x1800e0ff0  jz      loc_1800E1106
0x1800e0ff6  mov     r14d, 208h
0x1800e0ffc  xor     edi, edi
0x1800e0ffe  mov     ecx, r14d
0x1800e1001  call    cs:__imp_DllAllocSplMem
0x1800e1007  mov     rbp, rax
0x1800e100a  test    rax, rax
0x1800e100d  jz      loc_1800E1110
0x1800e1013  mov     r8, [rbx+18h]
0x1800e1017  xor     r9d, r9d
0x1800e101a  mov     edx, 104h; unsigned int
0x1800e101f  mov     rcx, rax; unsigned __int16 *
0x1800e1022  call    ?StrNCatBuffW@@YAKPEAGIZZ; StrNCatBuffW(ushort *,uint,...)
0x1800e1027  test    eax, eax
0x1800e1029  jnz     loc_1800E10FB
0x1800e102f  mov     rcx, rbp; unsigned __int16 *
0x1800e1032  call    ?LcmRemoveColon@@YAXPEAG@Z; LcmRemoveColon(ushort *)
0x1800e1037  call    cs:__imp_RevertToPrinterSelf
0x1800e103d  mov     rsi, rax
0x1800e1040  test    rax, rax
0x1800e1043  jz      loc_1800E10FB
0x1800e1049  mov     ecx, r14d
0x1800e104c  call    cs:__imp_DllAllocSplMem
0x1800e1052  mov     r14, rax
0x1800e1055  test    rax, rax
0x1800e1058  jz      loc_1800E10FB
0x1800e105e  mov     r8d, 104h; ucchMax
0x1800e1064  mov     rdx, rax; lpTargetPath
0x1800e1067  mov     rcx, rbp; lpDeviceName
0x1800e106a  call    cs:__imp_QueryDosDeviceW
0x1800e1070  test    eax, eax
0x1800e1072  jnz     short loc_1800E107F
0x1800e1074  mov     rcx, rsi; hToken
0x1800e1077  call    cs:__imp_ImpersonatePrinterClient
0x1800e107d  jmp     short loc_1800E10F2
0x1800e107f  mov     rdx, [rbx+38h]; lpString2
0x1800e1083  mov     rcx, r14; lpString1
0x1800e1086  call    cs:__imp_lstrcmpiW
0x1800e108c  test    eax, eax
0x1800e108e  jnz     short loc_1800E10A0
0x1800e1090  mov     rcx, rsi; hToken
0x1800e1093  call    cs:__imp_ImpersonatePrinterClient
0x1800e1099  mov     edi, 1
0x1800e109e  jmp     short loc_1800E10F2
0x1800e10a0  mov     rcx, rbx; struct _LCMINIPORT *
0x1800e10a3  call    ?RemoveDosDeviceDefinition@@YAHPEAU_LCMINIPORT@@@Z; RemoveDosDeviceDefinition(_LCMINIPORT *)
0x1800e10a8  mov     rcx, [rbx+20h]; hObject
0x1800e10ac  call    cs:__imp_CloseHandle
0x1800e10b2  mov     rcx, [rbx+60h]
0x1800e10b6  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x1800e10be  test    rcx, rcx
0x1800e10c1  jz      short loc_1800E10CD
0x1800e10c3  call    cs:__imp_SplUnregisterForDeviceEvents
0x1800e10c9  mov     [rbx+60h], rdi
0x1800e10cd  mov     rcx, [rbx+38h]
0x1800e10d1  and     dword ptr [rbx+2Ch], 0FFFFFFFCh
0x1800e10d5  call    cs:__imp_DllFreeSplStr
0x1800e10db  mov     rcx, rsi; hToken
0x1800e10de  mov     [rbx+38h], rdi
0x1800e10e2  call    cs:__imp_ImpersonatePrinterClient
0x1800e10e8  mov     rcx, rbx; struct _LCMINIPORT *
0x1800e10eb  call    ?ValidateDosDevicePort@@YAHPEAU_LCMINIPORT@@@Z; ValidateDosDevicePort(_LCMINIPORT *)
0x1800e10f0  mov     edi, eax
0x1800e10f2  mov     rcx, r14
0x1800e10f5  call    cs:__imp_DllFreeSplMem
0x1800e10fb  mov     rcx, rbp
0x1800e10fe  call    cs:__imp_DllFreeSplMem
0x1800e1104  jmp     short loc_1800E1110
0x1800e1106  mov     rcx, rbx; struct _LCMINIPORT *
0x1800e1109  call    ?ValidateDosDevicePort@@YAHPEAU_LCMINIPORT@@@Z; ValidateDosDevicePort(_LCMINIPORT *)
0x1800e110e  mov     edi, eax
0x1800e1110  mov     eax, edi
0x1800e1112  add     rsp, 20h
0x1800e1116  pop     r14
0x1800e1118  pop     rdi
0x1800e1119  pop     rsi
0x1800e111a  pop     rbp
0x1800e111b  pop     rbx
0x1800e111c  retn
```
