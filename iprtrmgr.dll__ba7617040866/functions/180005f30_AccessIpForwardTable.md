# AccessIpForwardTable

- ea: `0x180005f30`
- end: `0x1800061e1`
- name: `AccessIpForwardTable`
- size: `689`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005f30`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000619d`
- `ntdll!RtlReleaseResource` at `0x18000619d`
- `ntdll!RtlAcquireResourceShared` at `0x180006085`
- `ntdll!RtlAcquireResourceShared` at `0x180006085`

## string_xrefs

- `0x180005f9b`: `AccessIpForwardTable`
- `0x180005ff7`: `Leaving: AccessIpForwardTable`
- `0x1800061ac`: `Leaving: AccessIpForwardTable`
- `0x180006034`: `AccessIpForwardTable: Couldnt update IpForward Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessIpForwardTable(
        int a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5,
        __int64 a6,
        int a7)
{
  char v9; // al
  unsigned int updated; // eax
  unsigned int v12; // ebx
  char v13; // cl
  bool v14; // zf
  unsigned __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // r8d
  char *v20; // rdx
  int i; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // [rsp+30h] [rbp-848h] BYREF
  char v25[2044]; // [rsp+34h] [rbp-844h] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Entered: %ws", L"AccessIpForwardTable");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    updated = UpdateCache(1, a6);
    v12 = updated;
    if ( updated )
    {
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"AccessIpForwardTable: Couldnt update IpForward Cache. Error %d", updated);
        v13 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v24);
          v13 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v14 = v13 >= 0;
    }
    else
    {
      RtlAcquireResourceShared(&stru_18008C260, 1u);
      if ( qword_18008C7E8 && *(_DWORD *)qword_18008C7E8 )
      {
        v15 = 56LL * *(unsigned int *)qword_18008C7E8;
        if ( v15 > 0xFFFFFFFF || (v16 = v15 + 8, (int)v15 + 8 < (unsigned int)v15) || (v17 = v15 + 12, v16 + 4 < v16) )
        {
          v12 = 534;
        }
        else
        {
          v18 = v16 + 12;
          if ( v17 + 8 >= v17 )
          {
            if ( *a4 >= v18 )
            {
              *a5 = 7;
              v19 = 0;
              *a4 = v18;
              v20 = (char *)qword_18008C7E8;
              for ( i = *(_DWORD *)qword_18008C7E8; v19 < *(_DWORD *)qword_18008C7E8; i = *(_DWORD *)qword_18008C7E8 )
              {
                v22 = v19++;
                v23 = 14 * v22;
                *(_OWORD *)&a5[v23 + 3] = *(_OWORD *)&v20[56 * v22 + 4];
                *(_OWORD *)&a5[v23 + 7] = *(_OWORD *)&v20[56 * v22 + 20];
                *(_OWORD *)&a5[v23 + 11] = *(_OWORD *)&v20[56 * v22 + 36];
                *(_QWORD *)&a5[v23 + 15] = *(_QWORD *)&v20[56 * v22 + 52];
                v20 = (char *)qword_18008C7E8;
              }
              a5[2] = i;
              v12 = 0;
            }
            else
            {
              *a4 = v18;
              v12 = 122;
            }
          }
          else
          {
            v12 = 534;
          }
        }
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"No valid entries found");
        if ( *a4 >= 0x44 )
        {
          *a5 = 7;
          v12 = 0;
          a5[2] = 0;
        }
        else
        {
          v12 = 122;
        }
        *a4 = 68;
      }
      RtlReleaseResource(&stru_18008C260);
      v14 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v14 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpForwardTable");
    return v12;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpForwardTable");
    return 87;
  }
}

```

## disassembly

```asm
0x180005f30  push    rbx
0x180005f32  push    rsi
0x180005f33  push    rdi
0x180005f34  push    r12
0x180005f36  push    r14
0x180005f38  push    r15
0x180005f3a  sub     rsp, 848h
0x180005f41  mov     rax, cs:__security_cookie
0x180005f48  xor     rax, rsp
0x180005f4b  mov     [rsp+878h+var_48], rax
0x180005f53  mov     rsi, [rsp+878h+arg_20]
0x180005f5b  mov     ebx, ecx
0x180005f5d  mov     r14, [rsp+878h+arg_28]
0x180005f65  lea     rcx, [rsp+878h+var_844]; void *
0x180005f6a  xor     eax, eax
0x180005f6c  xor     edx, edx; Val
0x180005f6e  mov     r8d, 7FCh; Size
0x180005f74  mov     [rsp+878h+var_848], eax
0x180005f78  mov     rdi, r9
0x180005f7b  call    memset_0
0x180005f80  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005f87  lea     r12, RasRtrmgrTraceInfo
0x180005f8e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005f95  test    al, al
0x180005f97  jns     short loc_180005FDA
0x180005f99  xor     eax, eax
0x180005f9b  lea     r8, aAccessipforwar_2; "AccessIpForwardTable"
0x180005fa2  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005fa9  mov     word ptr [rsp+878h+var_848], ax
0x180005fae  lea     rcx, [rsp+878h+var_848]
0x180005fb3  call    FormatRRASErrorString
0x180005fb8  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005fbf  test    al, al
0x180005fc1  jns     short loc_180005FDA
0x180005fc3  lea     r8, [rsp+878h+var_848]
0x180005fc8  mov     rdx, r12
0x180005fcb  mov     rcx, r15
0x180005fce  call    McTemplateU0z_EventWriteTransfer
0x180005fd3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005fda  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x180005fe2  jnz     short loc_180005FEE
0x180005fe4  mov     eax, 32h ; '2'
0x180005fe9  jmp     loc_1800061C0
0x180005fee  cmp     ebx, 1
0x180005ff1  jz      short loc_180006013
0x180005ff3  test    al, 80h
0x180005ff5  jz      short loc_180006009
0x180005ff7  lea     r8, aLeavingAccessi_6; "Leaving: AccessIpForwardTable"
0x180005ffe  mov     rdx, r12
0x180006001  mov     rcx, r15
0x180006004  call    McTemplateU0z_EventWriteTransfer
0x180006009  mov     eax, 57h ; 'W'
0x18000600e  jmp     loc_1800061C0
0x180006013  mov     rdx, r14
0x180006016  mov     ecx, 1
0x18000601b  call    UpdateCache
0x180006020  mov     ebx, eax
0x180006022  test    eax, eax
0x180006024  jz      short loc_18000607C
0x180006026  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000602d  test    cl, 40h
0x180006030  jz      short loc_180006074
0x180006032  xor     ecx, ecx
0x180006034  lea     rdx, aAccessipforwar_3; "AccessIpForwardTable: Couldnt update Ip"...
0x18000603b  mov     word ptr [rsp+878h+var_848], cx
0x180006040  mov     r8d, eax
0x180006043  lea     rcx, [rsp+878h+var_848]
0x180006048  call    FormatRRASErrorString
0x18000604d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006054  test    cl, 40h
0x180006057  jz      short loc_180006074
0x180006059  lea     r8, [rsp+878h+var_848]
0x18000605e  mov     rcx, r15
0x180006061  lea     rdx, RasRtrMgrTraceError
0x180006068  call    McTemplateU0z_EventWriteTransfer
0x18000606d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006074  test    cl, 80h
0x180006077  jmp     loc_1800061AA
0x18000607c  mov     dl, 1; Wait
0x18000607e  lea     rcx, stru_18008C260; Resource
0x180006085  call    cs:__imp_RtlAcquireResourceShared
0x18000608b  mov     rax, cs:qword_18008C7E8
0x180006092  test    rax, rax
0x180006095  jz      loc_18000615A
0x18000609b  cmp     dword ptr [rax], 0
0x18000609e  jz      loc_18000615A
0x1800060a4  mov     eax, [rax]
0x1800060a6  imul    rcx, rax, 38h ; '8'
0x1800060aa  mov     eax, 0FFFFFFFFh
0x1800060af  cmp     rcx, rax
0x1800060b2  ja      loc_180006150
0x1800060b8  lea     eax, [rcx+8]
0x1800060bb  cmp     eax, ecx
0x1800060bd  jb      loc_180006150
0x1800060c3  lea     ecx, [rax+4]
0x1800060c6  cmp     ecx, eax
0x1800060c8  jb      loc_180006150
0x1800060ce  lea     eax, [rcx+8]
0x1800060d1  cmp     eax, ecx
0x1800060d3  jnb     short loc_1800060DF
0x1800060d5  mov     ebx, 216h
0x1800060da  jmp     loc_180006196
0x1800060df  cmp     [rdi], eax
0x1800060e1  jnb     short loc_1800060EF
0x1800060e3  mov     [rdi], eax
0x1800060e5  mov     ebx, 7Ah ; 'z'
0x1800060ea  jmp     loc_180006196
0x1800060ef  mov     dword ptr [rsi], 7
0x1800060f5  xor     r8d, r8d
0x1800060f8  mov     [rdi], eax
0x1800060fa  mov     rdx, cs:qword_18008C7E8
0x180006101  mov     eax, [rdx]
0x180006103  test    eax, eax
0x180006105  jz      short loc_180006149
0x180006107  mov     eax, r8d
0x18000610a  inc     r8d
0x18000610d  imul    rcx, rax, 38h ; '8'
0x180006111  movups  xmm0, xmmword ptr [rcx+rdx+4]
0x180006116  movups  xmmword ptr [rcx+rsi+0Ch], xmm0
0x18000611b  movups  xmm1, xmmword ptr [rcx+rdx+14h]
0x180006120  movups  xmmword ptr [rcx+rsi+1Ch], xmm1
0x180006125  movups  xmm0, xmmword ptr [rcx+rdx+24h]
0x18000612a  movups  xmmword ptr [rcx+rsi+2Ch], xmm0
0x18000612f  movsd   xmm1, qword ptr [rcx+rdx+34h]
0x180006135  movsd   qword ptr [rcx+rsi+3Ch], xmm1
0x18000613b  mov     rdx, cs:qword_18008C7E8
0x180006142  mov     eax, [rdx]
0x180006144  cmp     r8d, eax
0x180006147  jb      short loc_180006107
0x180006149  mov     [rsi+8], eax
0x18000614c  xor     ebx, ebx
0x18000614e  jmp     short loc_180006196
0x180006150  mov     eax, 80070216h
0x180006155  movzx   ebx, ax
0x180006158  jmp     short loc_180006196
0x18000615a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006161  jz      short loc_180006175
0x180006163  lea     r8, aNoValidEntries; "No valid entries found"
0x18000616a  mov     rdx, r12
0x18000616d  mov     rcx, r15
0x180006170  call    McTemplateU0z_EventWriteTransfer
0x180006175  cmp     dword ptr [rdi], 44h ; 'D'
0x180006178  jnb     short loc_180006181
0x18000617a  mov     ebx, 7Ah ; 'z'
0x18000617f  jmp     short loc_180006190
0x180006181  mov     dword ptr [rsi], 7
0x180006187  xor     ebx, ebx
0x180006189  mov     dword ptr [rsi+8], 0
0x180006190  mov     dword ptr [rdi], 44h ; 'D'
0x180006196  lea     rcx, stru_18008C260; Resource
0x18000619d  call    cs:__imp_RtlReleaseResource
0x1800061a3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800061aa  jz      short loc_1800061BE
0x1800061ac  lea     r8, aLeavingAccessi_6; "Leaving: AccessIpForwardTable"
0x1800061b3  mov     rdx, r12
0x1800061b6  mov     rcx, r15
0x1800061b9  call    McTemplateU0z_EventWriteTransfer
0x1800061be  mov     eax, ebx
0x1800061c0  mov     rcx, [rsp+878h+var_48]
0x1800061c8  xor     rcx, rsp; StackCookie
0x1800061cb  call    __security_check_cookie
0x1800061d0  add     rsp, 848h
0x1800061d7  pop     r15
0x1800061d9  pop     r14
0x1800061db  pop     r12
0x1800061dd  pop     rdi
0x1800061de  pop     rsi
0x1800061df  pop     rbx
0x1800061e0  retn
```
