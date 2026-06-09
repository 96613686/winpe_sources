# TeredoPowerStateChangeCallback

- ea: `0x180032180`
- end: `0x180032408`
- name: `TeredoPowerStateChangeCallback`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d7b0`
- `0x1800138ac`
- `0x180015a6c`
- `0x180032180`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800321a1`
- `ntdll!EtwEventActivityIdControl` at `0x1800321a1`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800321d0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800321d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800323c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800323c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003225a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003225a`

## string_xrefs

- `0x180032229`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180032272`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800323d3`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

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
0x180032180  push    rbx
0x180032182  push    rbp
0x180032183  push    rsi
0x180032184  push    rdi
0x180032185  push    r14
0x180032187  push    r15
0x180032189  sub     rsp, 48h
0x18003218d  mov     ebx, edx
0x18003218f  mov     rsi, rcx
0x180032192  lea     rdx, g_TeredoActivityId
0x180032199  mov     ecx, 2
0x18003219e  mov     rdi, r8
0x1800321a1  call    cs:__imp_EtwEventActivityIdControl
0x1800321a8  nop     dword ptr [rax+rax+00h]
0x1800321ad  cmp     ebx, 8013h
0x1800321b3  jnz     loc_1800323F8
0x1800321b9  mov     r14, [rsi+1EE0h]
0x1800321c0  lea     rdx, GUID_LOW_POWER_EPOCH; Source2
0x1800321c7  mov     r8d, 10h; Length
0x1800321cd  mov     rcx, rdi; Source1
0x1800321d0  call    cs:__imp_RtlCompareMemory
0x1800321d7  nop     dword ptr [rax+rax+00h]
0x1800321dc  cmp     rax, 10h
0x1800321e0  jz      short loc_1800321F8
0x1800321e2  lea     rdx, aTeredopowersta_4; "TeredoPowerStateChangeCallback received"...
0x1800321e9  mov     ecx, 100000h
0x1800321ee  call    EventWrite0
0x1800321f3  jmp     loc_1800323F8
0x1800321f8  mov     r8d, [rdi+10h]
0x1800321fc  cmp     r8d, 4
0x180032200  jz      short loc_180032218
0x180032202  lea     rdx, aTeredopowersta_0; "TeredoPowerStateChangeCallback received"...
0x180032209  mov     ecx, 100000h
0x18003220e  call    EventWrite0
0x180032213  jmp     loc_1800323F8
0x180032218  mov     ebp, [rdi+14h]
0x18003221b  lea     rax, aTeredopowersta_2; "TeredoPowerStateChangeCallback"
0x180032222  mov     rdi, cs:g_TeredoLock
0x180032229  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032230  mov     r15d, 10D7h
0x180032236  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18003223d  mov     r8, rdi
0x180032240  mov     dword ptr [rsp+78h+var_50], r15d
0x180032245  mov     ecx, 800000h
0x18003224a  mov     [rsp+78h+var_58], rax
0x18003224f  call    EventWrite0
0x180032254  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032257  mov     rcx, rdi; hHandle
0x18003225a  call    cs:__imp_WaitForSingleObject
0x180032261  nop     dword ptr [rax+rax+00h]
0x180032266  mov     r8, rdi
0x180032269  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180032270  mov     ebx, eax
0x180032272  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180032279  mov     dword ptr [rsp+78h+var_48], ebx
0x18003227d  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180032284  mov     dword ptr [rsp+78h+var_50], r15d
0x180032289  test    ebx, ebx
0x18003228b  mov     edi, 800000h
0x180032290  lea     r15, aTeredopowersta_2; "TeredoPowerStateChangeCallback"
0x180032297  cmovnz  rdx, rax
0x18003229b  mov     [rsp+78h+var_58], r15
0x1800322a0  mov     ecx, edi
0x1800322a2  call    EventWrite0
0x1800322a7  test    ebx, ebx
0x1800322a9  jz      short loc_1800322B7
0x1800322ab  lea     rdx, aTeredopowersta_1; "TeredoPowerStateChangeCallback couldn't"...
0x1800322b2  jmp     loc_1800321E9
0x1800322b7  mov     eax, ebp
0x1800322b9  test    ebp, ebp
0x1800322bb  jz      loc_180032347
0x1800322c1  cmp     eax, 1
0x1800322c4  jz      short loc_1800322DF
0x1800322c6  mov     r8d, ebp
0x1800322c9  lea     rdx, aTeredopowersta_5; "TeredoPowerStateChangeCallback received"...
0x1800322d0  mov     ecx, 100000h
0x1800322d5  call    EventWrite0
0x1800322da  jmp     loc_1800323B9
0x1800322df  mov     eax, [r14+0B34h]
0x1800322e6  lea     rdx, aTeredopowersta; "TeredoPowerStateChangeCallback: enterin"...
0x1800322ed  movzx   ecx, byte ptr [rsi+3839h]
0x1800322f4  movzx   r9d, byte ptr [rsi+21F9h]
0x1800322fc  movzx   r8d, byte ptr [rsi+383Ah]
0x180032304  mov     dword ptr [rsp+78h+var_48], eax
0x180032308  mov     eax, [rsi+2188h]
0x18003230e  mov     dword ptr [rsp+78h+var_50], eax
0x180032312  mov     dword ptr [rsp+78h+var_58], ecx
0x180032316  mov     ecx, 100000h
0x18003231b  call    EventWrite0
0x180032320  cmp     byte ptr [rsi+21F9h], 0
0x180032327  jnz     loc_1800323B9
0x18003232d  cmp     byte ptr [rsi+3839h], 0
0x180032334  mov     byte ptr [rsi+383Ah], 1
0x18003233b  jz      short loc_1800323B9
0x18003233d  mov     rcx, rsi
0x180032340  call    TeredoStopClient
0x180032345  jmp     short loc_1800323B9
0x180032347  mov     eax, [r14+0B34h]
0x18003234e  lea     rdx, aTeredopowersta_3; "TeredoPowerStateChangeCallback: exiting"...
0x180032355  movzx   ecx, byte ptr [rsi+3839h]
0x18003235c  movzx   r9d, byte ptr [rsi+21F9h]
0x180032364  movzx   r8d, byte ptr [rsi+383Ah]
0x18003236c  mov     dword ptr [rsp+78h+var_48], eax
0x180032370  mov     eax, [rsi+2188h]
0x180032376  mov     dword ptr [rsp+78h+var_50], eax
0x18003237a  mov     dword ptr [rsp+78h+var_58], ecx
0x18003237e  mov     ecx, 100000h
0x180032383  call    EventWrite0
0x180032388  cmp     byte ptr [rsi+383Ah], 0
0x18003238f  jz      short loc_1800323B9
0x180032391  cmp     byte ptr [rsi+21F9h], 0
0x180032398  mov     byte ptr [rsi+383Ah], 0
0x18003239f  jnz     short loc_1800323B9
0x1800323a1  cmp     byte ptr [rsi+3839h], 0
0x1800323a8  jz      short loc_1800323B9
0x1800323aa  xor     r8d, r8d
0x1800323ad  mov     rcx, rsi
0x1800323b0  lea     edx, [r8+1]
0x1800323b4  call    TeredoStartOrRefreshClient
0x1800323b9  mov     rbx, cs:g_TeredoLock
0x1800323c0  mov     rcx, rbx; hMutex
0x1800323c3  call    cs:__imp_ReleaseMutex
0x1800323ca  nop     dword ptr [rax+rax+00h]
0x1800323cf  mov     dword ptr [rsp+78h+var_48], eax
0x1800323d3  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800323da  mov     dword ptr [rsp+78h+var_50], 1115h
0x1800323e2  mov     r8, rbx
0x1800323e5  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x1800323ec  mov     [rsp+78h+var_58], r15
0x1800323f1  mov     ecx, edi
0x1800323f3  call    EventWrite0
0x1800323f8  xor     eax, eax
0x1800323fa  add     rsp, 48h
0x1800323fe  pop     r15
0x180032400  pop     r14
0x180032402  pop     rdi
0x180032403  pop     rsi
0x180032404  pop     rbp
0x180032405  pop     rbx
0x180032406  retn
```
