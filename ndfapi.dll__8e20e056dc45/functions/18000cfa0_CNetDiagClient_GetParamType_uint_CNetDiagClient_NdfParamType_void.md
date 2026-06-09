# CNetDiagClient::GetParamType(uint,CNetDiagClient::NdfParamType *,void * *)

- ea: `0x18000cfa0`
- end: `0x18000d192`
- name: `?GetParamType@CNetDiagClient@@IEAAJIPEAW4NdfParamType@1@PEAPEAX@Z`
- size: `498`
- prototype: `__int64 __fastcall(CNetDiagClient *this, __int64, enum CNetDiagClient::NdfParamType *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000cd4c`
- `0x18000e0c4`
- `0x18000e2d4`
- `0x180016f30`

## callees

- `0x18000cfa0`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18000d041`
- `KERNEL32!lstrcmpW` at `0x18000d060`
- `KERNEL32!lstrcmpW` at `0x18000d07f`
- `KERNEL32!lstrcmpW` at `0x18000d09e`
- `KERNEL32!lstrcmpW` at `0x18000d0bd`
- `KERNEL32!lstrcmpW` at `0x18000d0dc`
- `KERNEL32!lstrcmpW` at `0x18000d0fb`
- `KERNEL32!lstrcmpW` at `0x18000d117`
- `KERNEL32!lstrcmpW` at `0x18000d133`
- `KERNEL32!lstrcmpW` at `0x18000d14f`
- `KERNEL32!lstrcmpW` at `0x18000d16b`
- `KERNEL32!lstrcmpW` at `0x18000d041`
- `KERNEL32!lstrcmpW` at `0x18000d060`
- `KERNEL32!lstrcmpW` at `0x18000d07f`
- `KERNEL32!lstrcmpW` at `0x18000d09e`
- `KERNEL32!lstrcmpW` at `0x18000d0bd`
- `KERNEL32!lstrcmpW` at `0x18000d0dc`
- `KERNEL32!lstrcmpW` at `0x18000d0fb`
- `KERNEL32!lstrcmpW` at `0x18000d117`
- `KERNEL32!lstrcmpW` at `0x18000d133`
- `KERNEL32!lstrcmpW` at `0x18000d14f`
- `KERNEL32!lstrcmpW` at `0x18000d16b`
- `ole32!CoTaskMemAlloc` at `0x18000d004`
- `ole32!CoTaskMemAlloc` at `0x18000d004`
- `ole32!CoTaskMemFree` at `0x18000d180`
- `ole32!CoTaskMemFree` at `0x18000d180`
- `wdi!WdiGetParameterByIndex` at `0x18000cfc4`
- `wdi!WdiGetParameterByIndex` at `0x18000cfc4`
- `wdi!WdiGetParameterName` at `0x18000cfed`
- `wdi!WdiGetParameterName` at `0x18000d027`
- `wdi!WdiGetParameterName` at `0x18000cfed`
- `wdi!WdiGetParameterName` at `0x18000d027`

## string_xrefs

- `0x18000d161`: `RepairState`
- `0x18000d10d`: `SelectedRepairGUID`
- `0x18000d056`: `NDFRepairOption`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::GetParamType(
        CNetDiagClient *this,
        __int64 a2,
        enum CNetDiagClient::NdfParamType *a3,
        void **a4)
{
  __int64 v4; // rcx
  WCHAR *v7; // rbx
  int ParameterByIndex; // esi
  WCHAR *v9; // rax
  int v10; // eax
  int v11; // ecx
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 16);
  v13 = 0;
  v7 = 0;
  ParameterByIndex = WdiGetParameterByIndex(v4, a2, a4);
  if ( ParameterByIndex >= 0 )
  {
    if ( *a4 )
    {
      ParameterByIndex = WdiGetParameterName(*a4, 0, &v13);
      if ( ParameterByIndex >= 0 )
      {
        v9 = (WCHAR *)CoTaskMemAlloc(2LL * v13);
        v7 = v9;
        if ( v9 )
        {
          ParameterByIndex = WdiGetParameterName(*a4, v9, &v13);
          if ( ParameterByIndex >= 0 )
          {
            if ( lstrcmpW(v7, L"NDFRootCause") )
            {
              if ( lstrcmpW(v7, L"NDFRepairOption") )
              {
                if ( lstrcmpW(v7, L"NDFRootCauseInfo") )
                {
                  if ( lstrcmpW(v7, L"NDFTraceFile") )
                  {
                    if ( lstrcmpW(v7, L"NDFStopStatus") )
                    {
                      if ( lstrcmpW(v7, L"NdfOptions") )
                      {
                        if ( lstrcmpW(v7, L"NDFCallResult") )
                        {
                          if ( lstrcmpW(v7, L"SelectedRepairGUID") )
                          {
                            if ( lstrcmpW(v7, L"RootCauseIndex") )
                            {
                              if ( lstrcmpW(v7, L"FollowUpIncident") )
                              {
                                v10 = lstrcmpW(v7, L"RepairState");
                                v11 = 0;
                                if ( !v10 )
                                  v11 = 11;
                                *(_DWORD *)a3 = v11;
                              }
                              else
                              {
                                *(_DWORD *)a3 = 10;
                              }
                            }
                            else
                            {
                              *(_DWORD *)a3 = 9;
                            }
                          }
                          else
                          {
                            *(_DWORD *)a3 = 8;
                          }
                        }
                        else
                        {
                          *(_DWORD *)a3 = 7;
                        }
                      }
                      else
                      {
                        *(_DWORD *)a3 = 6;
                      }
                    }
                    else
                    {
                      *(_DWORD *)a3 = 5;
                    }
                  }
                  else
                  {
                    *(_DWORD *)a3 = 4;
                  }
                }
                else
                {
                  *(_DWORD *)a3 = 3;
                }
              }
              else
              {
                *(_DWORD *)a3 = 2;
              }
            }
            else
            {
              *(_DWORD *)a3 = 1;
            }
          }
        }
        else
        {
          ParameterByIndex = -2147024882;
        }
      }
    }
    else
    {
      ParameterByIndex = -2147024809;
    }
  }
  CoTaskMemFree(v7);
  return (unsigned int)ParameterByIndex;
}

```

## disassembly

```asm
0x18000cfa0  push    rbx
0x18000cfa2  push    rsi
0x18000cfa3  push    rdi
0x18000cfa4  push    r14
0x18000cfa6  sub     rsp, 28h
0x18000cfaa  mov     rcx, [rcx+80h]
0x18000cfb1  mov     rdi, r8
0x18000cfb4  mov     r8, r9
0x18000cfb7  mov     [rsp+48h+arg_0], 0
0x18000cfbf  mov     r14, r9
0x18000cfc2  xor     ebx, ebx
0x18000cfc4  call    cs:__imp_WdiGetParameterByIndex
0x18000cfca  mov     esi, eax
0x18000cfcc  test    eax, eax
0x18000cfce  js      loc_18000D17D
0x18000cfd4  mov     rcx, [r14]
0x18000cfd7  test    rcx, rcx
0x18000cfda  jnz     short loc_18000CFE6
0x18000cfdc  mov     esi, 80070057h
0x18000cfe1  jmp     loc_18000D17D
0x18000cfe6  lea     r8, [rsp+48h+arg_0]
0x18000cfeb  xor     edx, edx
0x18000cfed  call    cs:__imp_WdiGetParameterName
0x18000cff3  mov     esi, eax
0x18000cff5  test    eax, eax
0x18000cff7  js      loc_18000D17D
0x18000cffd  mov     ecx, [rsp+48h+arg_0]
0x18000d001  add     rcx, rcx; cb
0x18000d004  call    cs:__imp_CoTaskMemAlloc
0x18000d00a  mov     rbx, rax
0x18000d00d  test    rax, rax
0x18000d010  jnz     short loc_18000D01C
0x18000d012  mov     esi, 8007000Eh
0x18000d017  jmp     loc_18000D17D
0x18000d01c  mov     rcx, [r14]
0x18000d01f  lea     r8, [rsp+48h+arg_0]
0x18000d024  mov     rdx, rbx
0x18000d027  call    cs:__imp_WdiGetParameterName
0x18000d02d  mov     esi, eax
0x18000d02f  test    eax, eax
0x18000d031  js      loc_18000D17D
0x18000d037  lea     rdx, aNdfrootcause; "NDFRootCause"
0x18000d03e  mov     rcx, rbx; lpString1
0x18000d041  call    cs:__imp_lstrcmpW
0x18000d047  test    eax, eax
0x18000d049  jnz     short loc_18000D056
0x18000d04b  mov     dword ptr [rdi], 1
0x18000d051  jmp     loc_18000D17D
0x18000d056  lea     rdx, aNdfrepairoptio; "NDFRepairOption"
0x18000d05d  mov     rcx, rbx; lpString1
0x18000d060  call    cs:__imp_lstrcmpW
0x18000d066  test    eax, eax
0x18000d068  jnz     short loc_18000D075
0x18000d06a  mov     dword ptr [rdi], 2
0x18000d070  jmp     loc_18000D17D
0x18000d075  lea     rdx, aNdfrootcausein; "NDFRootCauseInfo"
0x18000d07c  mov     rcx, rbx; lpString1
0x18000d07f  call    cs:__imp_lstrcmpW
0x18000d085  test    eax, eax
0x18000d087  jnz     short loc_18000D094
0x18000d089  mov     dword ptr [rdi], 3
0x18000d08f  jmp     loc_18000D17D
0x18000d094  lea     rdx, aNdftracefile; "NDFTraceFile"
0x18000d09b  mov     rcx, rbx; lpString1
0x18000d09e  call    cs:__imp_lstrcmpW
0x18000d0a4  test    eax, eax
0x18000d0a6  jnz     short loc_18000D0B3
0x18000d0a8  mov     dword ptr [rdi], 4
0x18000d0ae  jmp     loc_18000D17D
0x18000d0b3  lea     rdx, aNdfstopstatus; "NDFStopStatus"
0x18000d0ba  mov     rcx, rbx; lpString1
0x18000d0bd  call    cs:__imp_lstrcmpW
0x18000d0c3  test    eax, eax
0x18000d0c5  jnz     short loc_18000D0D2
0x18000d0c7  mov     dword ptr [rdi], 5
0x18000d0cd  jmp     loc_18000D17D
0x18000d0d2  lea     rdx, aNdfoptions; "NdfOptions"
0x18000d0d9  mov     rcx, rbx; lpString1
0x18000d0dc  call    cs:__imp_lstrcmpW
0x18000d0e2  test    eax, eax
0x18000d0e4  jnz     short loc_18000D0F1
0x18000d0e6  mov     dword ptr [rdi], 6
0x18000d0ec  jmp     loc_18000D17D
0x18000d0f1  lea     rdx, aNdfcallresult; "NDFCallResult"
0x18000d0f8  mov     rcx, rbx; lpString1
0x18000d0fb  call    cs:__imp_lstrcmpW
0x18000d101  test    eax, eax
0x18000d103  jnz     short loc_18000D10D
0x18000d105  mov     dword ptr [rdi], 7
0x18000d10b  jmp     short loc_18000D17D
0x18000d10d  lea     rdx, aSelectedrepair; "SelectedRepairGUID"
0x18000d114  mov     rcx, rbx; lpString1
0x18000d117  call    cs:__imp_lstrcmpW
0x18000d11d  test    eax, eax
0x18000d11f  jnz     short loc_18000D129
0x18000d121  mov     dword ptr [rdi], 8
0x18000d127  jmp     short loc_18000D17D
0x18000d129  lea     rdx, aRootcauseindex; "RootCauseIndex"
0x18000d130  mov     rcx, rbx; lpString1
0x18000d133  call    cs:__imp_lstrcmpW
0x18000d139  test    eax, eax
0x18000d13b  jnz     short loc_18000D145
0x18000d13d  mov     dword ptr [rdi], 9
0x18000d143  jmp     short loc_18000D17D
0x18000d145  lea     rdx, aFollowupincide; "FollowUpIncident"
0x18000d14c  mov     rcx, rbx; lpString1
0x18000d14f  call    cs:__imp_lstrcmpW
0x18000d155  test    eax, eax
0x18000d157  jnz     short loc_18000D161
0x18000d159  mov     dword ptr [rdi], 0Ah
0x18000d15f  jmp     short loc_18000D17D
0x18000d161  lea     rdx, aRepairstate; "RepairState"
0x18000d168  mov     rcx, rbx; lpString1
0x18000d16b  call    cs:__imp_lstrcmpW
0x18000d171  xor     ecx, ecx
0x18000d173  test    eax, eax
0x18000d175  lea     edx, [rcx+0Bh]
0x18000d178  cmovz   ecx, edx
0x18000d17b  mov     [rdi], ecx
0x18000d17d  mov     rcx, rbx; pv
0x18000d180  call    cs:__imp_CoTaskMemFree
0x18000d186  mov     eax, esi
0x18000d188  add     rsp, 28h
0x18000d18c  pop     r14
0x18000d18e  pop     rdi
0x18000d18f  pop     rsi
0x18000d190  pop     rbx
0x18000d191  retn
```
