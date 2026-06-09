# TeredoPowerStateChangeCallback

- ea: `0x180032190`
- end: `0x180032418`
- name: `TeredoPowerStateChangeCallback`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d7c0`
- `0x1800138bc`
- `0x180015a7c`
- `0x180032190`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800321b1`
- `ntdll!EtwEventActivityIdControl` at `0x1800321b1`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800321e0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800321e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800323d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800323d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003226a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003226a`

## string_xrefs

- `0x180032239`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180032282`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800323e3`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c
__int64 __fastcall TeredoPowerStateChangeCallback(__int64 a1, int a2, _DWORD *a3)
{
  __int64 v6; // r14
  unsigned int v7; // ebp
  HANDLE v8; // rdi
  DWORD v9; // eax
  const wchar_t *v10; // rdx
  DWORD v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  bool v14; // zf
  HANDLE v15; // rbx
  __int64 v17; // [rsp+20h] [rbp-58h]
  __int64 v18; // [rsp+28h] [rbp-50h]
  __int64 v19; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-48h]

  EtwEventActivityIdControl(2, g_TeredoActivityId);
  if ( a2 == 32787 )
  {
    v6 = *(_QWORD *)(a1 + 7904);
    if ( RtlCompareMemory(a3, &GUID_LOW_POWER_EPOCH, 0x10u) == 16 )
    {
      if ( a3[4] == 4 )
      {
        v7 = a3[5];
        v8 = g_TeredoLock;
        EventWrite0(
          0x800000,
          L"Get lock (%p) invoked at %S : %S : %u",
          g_TeredoLock,
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
          "TeredoPowerStateChangeCallback",
          4311);
        v9 = WaitForSingleObject(v8, 0xFFFFFFFF);
        v10 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
        v11 = v9;
        LODWORD(v18) = 4311;
        if ( v9 )
          v10 = L"Lock (%p) failed at %S : %S : %u. Return %d";
        EventWrite0(
          0x800000,
          v10,
          v8,
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
          "TeredoPowerStateChangeCallback",
          v18,
          v9);
        if ( v11 )
        {
          EventWrite0(0x100000, L"TeredoPowerStateChangeCallback couldn't acquire Teredo lock");
        }
        else
        {
          if ( v7 )
          {
            if ( v7 == 1 )
            {
              LODWORD(v20) = *(_DWORD *)(v6 + 2868);
              LODWORD(v19) = *(_DWORD *)(a1 + 8584);
              LODWORD(v17) = *(unsigned __int8 *)(a1 + 14393);
              EventWrite0(
                0x100000,
                L"TeredoPowerStateChangeCallback: entering low power epoch (was %i, allowed %i, initted %i, state %i, error type %i)",
                *(unsigned __int8 *)(a1 + 14394),
                *(unsigned __int8 *)(a1 + 8697),
                v17,
                v19,
                v20);
              if ( !*(_BYTE *)(a1 + 8697) )
              {
                v14 = *(_BYTE *)(a1 + 14393) == 0;
                *(_BYTE *)(a1 + 14394) = 1;
                if ( !v14 )
                  TeredoStopClient(a1, v12, v13);
              }
            }
            else
            {
              EventWrite0(0x100000, L"TeredoPowerStateChangeCallback received unrecognized notification %u", v7);
            }
          }
          else
          {
            LODWORD(v20) = *(_DWORD *)(v6 + 2868);
            LODWORD(v19) = *(_DWORD *)(a1 + 8584);
            LODWORD(v17) = *(unsigned __int8 *)(a1 + 14393);
            EventWrite0(
              0x100000,
              L"TeredoPowerStateChangeCallback: exiting low power epoch (was %i, allowed %i, initted %i, state %i, error type %i)",
              *(unsigned __int8 *)(a1 + 14394),
              *(unsigned __int8 *)(a1 + 8697),
              v17,
              v19,
              v20);
            if ( *(_BYTE *)(a1 + 14394) )
            {
              v14 = *(_BYTE *)(a1 + 8697) == 0;
              *(_BYTE *)(a1 + 14394) = 0;
              if ( v14 )
              {
                if ( *(_BYTE *)(a1 + 14393) )
                  TeredoStartOrRefreshClient((PVOID)a1);
              }
            }
          }
          v15 = g_TeredoLock;
          LODWORD(v20) = ReleaseMutex(g_TeredoLock);
          LODWORD(v19) = 4373;
          EventWrite0(
            0x800000,
            L"Lock (%p) released at %S : %S : %u. Return %d",
            v15,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
            "TeredoPowerStateChangeCallback",
            v19,
            v20);
        }
      }
      else
      {
        EventWrite0(0x100000, L"TeredoPowerStateChangeCallback received unexpected low power epoch data length %u");
      }
    }
    else
    {
      EventWrite0(0x100000, L"TeredoPowerStateChangeCallback received unsupported power setting GUID");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180032190  push    rbx
0x180032192  push    rbp
0x180032193  push    rsi
0x180032194  push    rdi
0x180032195  push    r14
0x180032197  push    r15
0x180032199  sub     rsp, 48h
0x18003219d  mov     ebx, edx
0x18003219f  mov     rsi, rcx
0x1800321a2  lea     rdx, g_TeredoActivityId
0x1800321a9  mov     ecx, 2
0x1800321ae  mov     rdi, r8
0x1800321b1  call    cs:__imp_EtwEventActivityIdControl
0x1800321b8  nop     dword ptr [rax+rax+00h]
0x1800321bd  cmp     ebx, 8013h
0x1800321c3  jnz     loc_180032408
0x1800321c9  mov     r14, [rsi+1EE0h]
0x1800321d0  lea     rdx, GUID_LOW_POWER_EPOCH; Source2
0x1800321d7  mov     r8d, 10h; Length
0x1800321dd  mov     rcx, rdi; Source1
0x1800321e0  call    cs:__imp_RtlCompareMemory
0x1800321e7  nop     dword ptr [rax+rax+00h]
0x1800321ec  cmp     rax, 10h
0x1800321f0  jz      short loc_180032208
0x1800321f2  lea     rdx, aTeredopowersta_4; "TeredoPowerStateChangeCallback received"...
0x1800321f9  mov     ecx, 100000h
0x1800321fe  call    EventWrite0
0x180032203  jmp     loc_180032408
0x180032208  mov     r8d, [rdi+10h]
0x18003220c  cmp     r8d, 4
0x180032210  jz      short loc_180032228
0x180032212  lea     rdx, aTeredopowersta_0; "TeredoPowerStateChangeCallback received"...
0x180032219  mov     ecx, 100000h
0x18003221e  call    EventWrite0
0x180032223  jmp     loc_180032408
0x180032228  mov     ebp, [rdi+14h]
0x18003222b  lea     rax, aTeredopowersta_2; "TeredoPowerStateChangeCallback"
0x180032232  mov     rdi, cs:g_TeredoLock
0x180032239  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032240  mov     r15d, 10D7h
0x180032246  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18003224d  mov     r8, rdi
0x180032250  mov     dword ptr [rsp+78h+var_50], r15d
0x180032255  mov     ecx, 800000h
0x18003225a  mov     [rsp+78h+var_58], rax
0x18003225f  call    EventWrite0
0x180032264  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032267  mov     rcx, rdi; hHandle
0x18003226a  call    cs:__imp_WaitForSingleObject
0x180032271  nop     dword ptr [rax+rax+00h]
0x180032276  mov     r8, rdi
0x180032279  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180032280  mov     ebx, eax
0x180032282  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032289  mov     dword ptr [rsp+78h+var_48], ebx
0x18003228d  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180032294  mov     dword ptr [rsp+78h+var_50], r15d
0x180032299  test    ebx, ebx
0x18003229b  mov     edi, 800000h
0x1800322a0  lea     r15, aTeredopowersta_2; "TeredoPowerStateChangeCallback"
0x1800322a7  cmovnz  rdx, rax
0x1800322ab  mov     [rsp+78h+var_58], r15
0x1800322b0  mov     ecx, edi
0x1800322b2  call    EventWrite0
0x1800322b7  test    ebx, ebx
0x1800322b9  jz      short loc_1800322C7
0x1800322bb  lea     rdx, aTeredopowersta_1; "TeredoPowerStateChangeCallback couldn't"...
0x1800322c2  jmp     loc_1800321F9
0x1800322c7  mov     eax, ebp
0x1800322c9  test    ebp, ebp
0x1800322cb  jz      loc_180032357
0x1800322d1  cmp     eax, 1
0x1800322d4  jz      short loc_1800322EF
0x1800322d6  mov     r8d, ebp
0x1800322d9  lea     rdx, aTeredopowersta_5; "TeredoPowerStateChangeCallback received"...
0x1800322e0  mov     ecx, 100000h
0x1800322e5  call    EventWrite0
0x1800322ea  jmp     loc_1800323C9
0x1800322ef  mov     eax, [r14+0B34h]
0x1800322f6  lea     rdx, aTeredopowersta; "TeredoPowerStateChangeCallback: enterin"...
0x1800322fd  movzx   ecx, byte ptr [rsi+3839h]
0x180032304  movzx   r9d, byte ptr [rsi+21F9h]
0x18003230c  movzx   r8d, byte ptr [rsi+383Ah]
0x180032314  mov     dword ptr [rsp+78h+var_48], eax
0x180032318  mov     eax, [rsi+2188h]
0x18003231e  mov     dword ptr [rsp+78h+var_50], eax
0x180032322  mov     dword ptr [rsp+78h+var_58], ecx
0x180032326  mov     ecx, 100000h
0x18003232b  call    EventWrite0
0x180032330  cmp     byte ptr [rsi+21F9h], 0
0x180032337  jnz     loc_1800323C9
0x18003233d  cmp     byte ptr [rsi+3839h], 0
0x180032344  mov     byte ptr [rsi+383Ah], 1
0x18003234b  jz      short loc_1800323C9
0x18003234d  mov     rcx, rsi
0x180032350  call    TeredoStopClient
0x180032355  jmp     short loc_1800323C9
0x180032357  mov     eax, [r14+0B34h]
0x18003235e  lea     rdx, aTeredopowersta_3; "TeredoPowerStateChangeCallback: exiting"...
0x180032365  movzx   ecx, byte ptr [rsi+3839h]
0x18003236c  movzx   r9d, byte ptr [rsi+21F9h]
0x180032374  movzx   r8d, byte ptr [rsi+383Ah]
0x18003237c  mov     dword ptr [rsp+78h+var_48], eax
0x180032380  mov     eax, [rsi+2188h]
0x180032386  mov     dword ptr [rsp+78h+var_50], eax
0x18003238a  mov     dword ptr [rsp+78h+var_58], ecx
0x18003238e  mov     ecx, 100000h
0x180032393  call    EventWrite0
0x180032398  cmp     byte ptr [rsi+383Ah], 0
0x18003239f  jz      short loc_1800323C9
0x1800323a1  cmp     byte ptr [rsi+21F9h], 0
0x1800323a8  mov     byte ptr [rsi+383Ah], 0
0x1800323af  jnz     short loc_1800323C9
0x1800323b1  cmp     byte ptr [rsi+3839h], 0
0x1800323b8  jz      short loc_1800323C9
0x1800323ba  xor     r8d, r8d
0x1800323bd  mov     rcx, rsi
0x1800323c0  lea     edx, [r8+1]
0x1800323c4  call    TeredoStartOrRefreshClient
0x1800323c9  mov     rbx, cs:g_TeredoLock
0x1800323d0  mov     rcx, rbx; hMutex
0x1800323d3  call    cs:__imp_ReleaseMutex
0x1800323da  nop     dword ptr [rax+rax+00h]
0x1800323df  mov     dword ptr [rsp+78h+var_48], eax
0x1800323e3  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800323ea  mov     dword ptr [rsp+78h+var_50], 1115h
0x1800323f2  mov     r8, rbx
0x1800323f5  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x1800323fc  mov     [rsp+78h+var_58], r15
0x180032401  mov     ecx, edi
0x180032403  call    EventWrite0
0x180032408  xor     eax, eax
0x18003240a  add     rsp, 48h
0x18003240e  pop     r15
0x180032410  pop     r14
0x180032412  pop     rdi
0x180032413  pop     rsi
0x180032414  pop     rbp
0x180032415  pop     rbx
0x180032416  retn
```
