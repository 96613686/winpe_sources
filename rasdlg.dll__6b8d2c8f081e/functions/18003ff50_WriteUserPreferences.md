# WriteUserPreferences

- ea: `0x18003ff50`
- end: `0x180040527`
- name: `WriteUserPreferences`
- size: `1495`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ebf4`

## callees

- `0x18003f830`
- `0x18003fc44`
- `0x18003ff50`
- `0x180041880`
- `0x1800419a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ffb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ffe5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040019`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004004d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040081`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800400b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800400e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004011d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040151`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800401b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800401ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040221`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040255`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040289`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040325`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004035c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040393`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800403ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ffb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ffe5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040019`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004004d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040081`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800400b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800400e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004011d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040151`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800401b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800401ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040221`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040255`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040289`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040325`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004035c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040393`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800403ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800404e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800404e6`
- `rtutils!TracePrintfExA` at `0x18003ff82`
- `rtutils!TracePrintfExA` at `0x18004050c`
- `rtutils!TracePrintfExA` at `0x18003ff82`
- `rtutils!TracePrintfExA` at `0x18004050c`

## string_xrefs

- `0x180040164`: `SkipConnectComplete`
- `0x180040198`: `RedialAttempts`
- `0x180040234`: `RedialOnLinkFailure`
- `0x1800404dc`: `PersonalPhonebookPath`
- `0x1800404ab`: `AlternatePhonebookPath`
- `0x18003ff76`: `WriteUserPreferences`
- `0x180040500`: `WriteUserPreferences=%d`

## pseudocode

```c
__int64 __fastcall WriteUserPreferences(HKEY hKey, int *a2)
{
  unsigned int v4; // ebx
  int Data; // [rsp+58h] [rbp+28h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WriteUserPreferences");
  Data = *a2;
  v4 = RegSetValueExW(hKey, L"OperatorDial", 0, 4u, (const BYTE *)&Data, 4u);
  if ( !v4 )
  {
    Data = a2[1];
    v4 = RegSetValueExW(hKey, L"PreviewPhoneNumber", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v4 )
    {
      Data = a2[2];
      v4 = RegSetValueExW(hKey, L"UseLocation", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v4 )
      {
        Data = a2[3];
        v4 = RegSetValueExW(hKey, L"ShowLights", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v4 )
        {
          Data = a2[4];
          v4 = RegSetValueExW(hKey, L"ShowConnectStatus", 0, 4u, (const BYTE *)&Data, 4u);
          if ( !v4 )
          {
            Data = a2[9];
            v4 = RegSetValueExW(hKey, L"NewEntryWizard", 0, 4u, (const BYTE *)&Data, 4u);
            if ( !v4 )
            {
              Data = a2[5];
              v4 = RegSetValueExW(hKey, L"CloseOnDial", 0, 4u, (const BYTE *)&Data, 4u);
              if ( !v4 )
              {
                Data = a2[6];
                v4 = RegSetValueExW(hKey, L"AllowLogonPhonebookEdits", 0, 4u, (const BYTE *)&Data, 4u);
                if ( !v4 )
                {
                  Data = a2[7];
                  v4 = RegSetValueExW(hKey, L"AllowLogonLocationEdits", 0, 4u, (const BYTE *)&Data, 4u);
                  if ( !v4 )
                  {
                    Data = a2[8];
                    v4 = RegSetValueExW(hKey, L"SkipConnectComplete", 0, 4u, (const BYTE *)&Data, 4u);
                    if ( !v4 )
                    {
                      Data = a2[10];
                      v4 = RegSetValueExW(hKey, L"RedialAttempts", 0, 4u, (const BYTE *)&Data, 4u);
                      if ( !v4 )
                      {
                        Data = a2[11];
                        v4 = RegSetValueExW(hKey, L"RedialSeconds", 0, 4u, (const BYTE *)&Data, 4u);
                        if ( !v4 )
                        {
                          Data = a2[12];
                          v4 = RegSetValueExW(hKey, L"IdleHangUpSeconds", 0, 4u, (const BYTE *)&Data, 4u);
                          if ( !v4 )
                          {
                            Data = a2[13];
                            v4 = RegSetValueExW(hKey, L"RedialOnLinkFailure", 0, 4u, (const BYTE *)&Data, 4u);
                            if ( !v4 )
                            {
                              Data = a2[14];
                              v4 = RegSetValueExW(hKey, L"PopupOnTopWhenRedialing", 0, 4u, (const BYTE *)&Data, 4u);
                              if ( !v4 )
                              {
                                Data = a2[15];
                                v4 = RegSetValueExW(hKey, L"ExpandAutoDialQuery", 0, 4u, (const BYTE *)&Data, 4u);
                                if ( !v4 )
                                {
                                  Data = a2[16];
                                  v4 = RegSetValueExW(hKey, L"CallbackMode", 0, 4u, (const BYTE *)&Data, 4u);
                                  if ( !v4 )
                                  {
                                    Data = a2[22];
                                    v4 = RegSetValueExW(hKey, L"PhonebookMode", 0, 4u, (const BYTE *)&Data, 4u);
                                    if ( !v4 )
                                    {
                                      Data = a2[32];
                                      v4 = RegSetValueExW(hKey, L"UseAreaAndCountry", 0, 4u, (const BYTE *)&Data, 4u);
                                      if ( !v4 )
                                      {
                                        Data = a2[40];
                                        v4 = RegSetValueExW(hKey, L"WindowX", 0, 4u, (const BYTE *)&Data, 4u);
                                        if ( !v4 )
                                        {
                                          Data = a2[41];
                                          RegSetValueExW(hKey, L"WindowY", 0, 4u, (const BYTE *)&Data, 4u);
                                          v4 = SetCallbackList(hKey, *((_QWORD *)a2 + 9));
                                          if ( !v4 )
                                          {
                                            v4 = SetRegMultiSz(hKey, L"Phonebooks");
                                            if ( !v4 )
                                            {
                                              v4 = SetRegMultiSz(hKey, L"AreaCodes");
                                              if ( !v4 )
                                              {
                                                v4 = SetRegMultiSz(hKey, L"Prefixes");
                                                if ( !v4 )
                                                {
                                                  v4 = SetRegMultiSz(hKey, L"Suffixes");
                                                  if ( !v4 )
                                                  {
                                                    v4 = SetLocationList(hKey, *((_QWORD *)a2 + 19));
                                                    if ( !v4 )
                                                    {
                                                      v4 = SetRegSz(hKey, L"LastCallbackByCaller");
                                                      if ( !v4 )
                                                      {
                                                        v4 = SetRegSz(hKey, L"PersonalPhonebookFile");
                                                        if ( !v4 )
                                                        {
                                                          v4 = SetRegSz(hKey, L"AlternatePhonebookPath");
                                                          if ( !v4 )
                                                          {
                                                            v4 = SetRegSz(hKey, L"DefaultEntry");
                                                            if ( !v4 )
                                                            {
                                                              RegDeleteValueW(hKey, L"PersonalPhonebookPath");
                                                              a2[45] = 0;
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WriteUserPreferences=%d", v4);
  return v4;
}

```

## disassembly

```asm
0x18003ff50  mov     [rsp-18h+arg_0], rbx
0x18003ff55  mov     [rsp-18h+arg_10], rsi
0x18003ff5a  push    rbp
0x18003ff5b  push    rdi
0x18003ff5c  push    r14
0x18003ff5e  mov     rbp, rsp
0x18003ff61  sub     rsp, 30h
0x18003ff65  mov     rsi, rcx
0x18003ff68  mov     rdi, rdx
0x18003ff6b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003ff71  cmp     ecx, 0FFFFFFFFh
0x18003ff74  jz      short loc_18003FF88
0x18003ff76  lea     r8, aWriteuserprefe; "WriteUserPreferences"
0x18003ff7d  mov     edx, 0Ch; dwFlags
0x18003ff82  call    cs:__imp_TracePrintfExA
0x18003ff88  mov     eax, [rdi]
0x18003ff8a  lea     rdx, aOperatordial; "OperatorDial"
0x18003ff91  mov     [rbp+Data], eax
0x18003ff94  mov     r14d, 4
0x18003ff9a  lea     rax, [rbp+Data]
0x18003ff9e  mov     [rsp+30h+cbData], r14d; cbData
0x18003ffa3  mov     r9d, r14d; dwType
0x18003ffa6  mov     [rsp+30h+lpData], rax; lpData
0x18003ffab  xor     r8d, r8d; Reserved
0x18003ffae  mov     rcx, rsi; hKey
0x18003ffb1  call    cs:__imp_RegSetValueExW
0x18003ffb7  mov     ebx, eax
0x18003ffb9  test    eax, eax
0x18003ffbb  jnz     loc_1800404F2
0x18003ffc1  mov     eax, [rdi+4]
0x18003ffc4  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x18003ffcb  mov     [rbp+Data], eax
0x18003ffce  mov     r9d, r14d; dwType
0x18003ffd1  lea     rax, [rbp+Data]
0x18003ffd5  mov     [rsp+30h+cbData], r14d; cbData
0x18003ffda  xor     r8d, r8d; Reserved
0x18003ffdd  mov     [rsp+30h+lpData], rax; lpData
0x18003ffe2  mov     rcx, rsi; hKey
0x18003ffe5  call    cs:__imp_RegSetValueExW
0x18003ffeb  mov     ebx, eax
0x18003ffed  test    eax, eax
0x18003ffef  jnz     loc_1800404F2
0x18003fff5  mov     eax, [rdi+8]
0x18003fff8  lea     rdx, aUselocation; "UseLocation"
0x18003ffff  mov     [rbp+Data], eax
0x180040002  mov     r9d, r14d; dwType
0x180040005  lea     rax, [rbp+Data]
0x180040009  mov     [rsp+30h+cbData], r14d; cbData
0x18004000e  xor     r8d, r8d; Reserved
0x180040011  mov     [rsp+30h+lpData], rax; lpData
0x180040016  mov     rcx, rsi; hKey
0x180040019  call    cs:__imp_RegSetValueExW
0x18004001f  mov     ebx, eax
0x180040021  test    eax, eax
0x180040023  jnz     loc_1800404F2
0x180040029  mov     eax, [rdi+0Ch]
0x18004002c  lea     rdx, aShowlights; "ShowLights"
0x180040033  mov     [rbp+Data], eax
0x180040036  mov     r9d, r14d; dwType
0x180040039  lea     rax, [rbp+Data]
0x18004003d  mov     [rsp+30h+cbData], r14d; cbData
0x180040042  xor     r8d, r8d; Reserved
0x180040045  mov     [rsp+30h+lpData], rax; lpData
0x18004004a  mov     rcx, rsi; hKey
0x18004004d  call    cs:__imp_RegSetValueExW
0x180040053  mov     ebx, eax
0x180040055  test    eax, eax
0x180040057  jnz     loc_1800404F2
0x18004005d  mov     eax, [rdi+10h]
0x180040060  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x180040067  mov     [rbp+Data], eax
0x18004006a  mov     r9d, r14d; dwType
0x18004006d  lea     rax, [rbp+Data]
0x180040071  mov     [rsp+30h+cbData], r14d; cbData
0x180040076  xor     r8d, r8d; Reserved
0x180040079  mov     [rsp+30h+lpData], rax; lpData
0x18004007e  mov     rcx, rsi; hKey
0x180040081  call    cs:__imp_RegSetValueExW
0x180040087  mov     ebx, eax
0x180040089  test    eax, eax
0x18004008b  jnz     loc_1800404F2
0x180040091  mov     eax, [rdi+24h]
0x180040094  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x18004009b  mov     [rbp+Data], eax
0x18004009e  mov     r9d, r14d; dwType
0x1800400a1  lea     rax, [rbp+Data]
0x1800400a5  mov     [rsp+30h+cbData], r14d; cbData
0x1800400aa  xor     r8d, r8d; Reserved
0x1800400ad  mov     [rsp+30h+lpData], rax; lpData
0x1800400b2  mov     rcx, rsi; hKey
0x1800400b5  call    cs:__imp_RegSetValueExW
0x1800400bb  mov     ebx, eax
0x1800400bd  test    eax, eax
0x1800400bf  jnz     loc_1800404F2
0x1800400c5  mov     eax, [rdi+14h]
0x1800400c8  lea     rdx, aCloseondial; "CloseOnDial"
0x1800400cf  mov     [rbp+Data], eax
0x1800400d2  mov     r9d, r14d; dwType
0x1800400d5  lea     rax, [rbp+Data]
0x1800400d9  mov     [rsp+30h+cbData], r14d; cbData
0x1800400de  xor     r8d, r8d; Reserved
0x1800400e1  mov     [rsp+30h+lpData], rax; lpData
0x1800400e6  mov     rcx, rsi; hKey
0x1800400e9  call    cs:__imp_RegSetValueExW
0x1800400ef  mov     ebx, eax
0x1800400f1  test    eax, eax
0x1800400f3  jnz     loc_1800404F2
0x1800400f9  mov     eax, [rdi+18h]
0x1800400fc  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x180040103  mov     [rbp+Data], eax
0x180040106  mov     r9d, r14d; dwType
0x180040109  lea     rax, [rbp+Data]
0x18004010d  mov     [rsp+30h+cbData], r14d; cbData
0x180040112  xor     r8d, r8d; Reserved
0x180040115  mov     [rsp+30h+lpData], rax; lpData
0x18004011a  mov     rcx, rsi; hKey
0x18004011d  call    cs:__imp_RegSetValueExW
0x180040123  mov     ebx, eax
0x180040125  test    eax, eax
0x180040127  jnz     loc_1800404F2
0x18004012d  mov     eax, [rdi+1Ch]
0x180040130  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x180040137  mov     [rbp+Data], eax
0x18004013a  mov     r9d, r14d; dwType
0x18004013d  lea     rax, [rbp+Data]
0x180040141  mov     [rsp+30h+cbData], r14d; cbData
0x180040146  xor     r8d, r8d; Reserved
0x180040149  mov     [rsp+30h+lpData], rax; lpData
0x18004014e  mov     rcx, rsi; hKey
0x180040151  call    cs:__imp_RegSetValueExW
0x180040157  mov     ebx, eax
0x180040159  test    eax, eax
0x18004015b  jnz     loc_1800404F2
0x180040161  mov     eax, [rdi+20h]
0x180040164  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x18004016b  mov     [rbp+Data], eax
0x18004016e  mov     r9d, r14d; dwType
0x180040171  lea     rax, [rbp+Data]
0x180040175  mov     [rsp+30h+cbData], r14d; cbData
0x18004017a  xor     r8d, r8d; Reserved
0x18004017d  mov     [rsp+30h+lpData], rax; lpData
0x180040182  mov     rcx, rsi; hKey
0x180040185  call    cs:__imp_RegSetValueExW
0x18004018b  mov     ebx, eax
0x18004018d  test    eax, eax
0x18004018f  jnz     loc_1800404F2
0x180040195  mov     eax, [rdi+28h]
0x180040198  lea     rdx, aRedialattempts; "RedialAttempts"
0x18004019f  mov     [rbp+Data], eax
0x1800401a2  mov     r9d, r14d; dwType
0x1800401a5  lea     rax, [rbp+Data]
0x1800401a9  mov     [rsp+30h+cbData], r14d; cbData
0x1800401ae  xor     r8d, r8d; Reserved
0x1800401b1  mov     [rsp+30h+lpData], rax; lpData
0x1800401b6  mov     rcx, rsi; hKey
0x1800401b9  call    cs:__imp_RegSetValueExW
0x1800401bf  mov     ebx, eax
0x1800401c1  test    eax, eax
0x1800401c3  jnz     loc_1800404F2
0x1800401c9  mov     eax, [rdi+2Ch]
0x1800401cc  lea     rdx, aRedialseconds; "RedialSeconds"
0x1800401d3  mov     [rbp+Data], eax
0x1800401d6  mov     r9d, r14d; dwType
0x1800401d9  lea     rax, [rbp+Data]
0x1800401dd  mov     [rsp+30h+cbData], r14d; cbData
0x1800401e2  xor     r8d, r8d; Reserved
0x1800401e5  mov     [rsp+30h+lpData], rax; lpData
0x1800401ea  mov     rcx, rsi; hKey
0x1800401ed  call    cs:__imp_RegSetValueExW
0x1800401f3  mov     ebx, eax
0x1800401f5  test    eax, eax
0x1800401f7  jnz     loc_1800404F2
0x1800401fd  mov     eax, [rdi+30h]
0x180040200  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x180040207  mov     [rbp+Data], eax
0x18004020a  mov     r9d, r14d; dwType
0x18004020d  lea     rax, [rbp+Data]
0x180040211  mov     [rsp+30h+cbData], r14d; cbData
0x180040216  xor     r8d, r8d; Reserved
0x180040219  mov     [rsp+30h+lpData], rax; lpData
0x18004021e  mov     rcx, rsi; hKey
0x180040221  call    cs:__imp_RegSetValueExW
0x180040227  mov     ebx, eax
0x180040229  test    eax, eax
0x18004022b  jnz     loc_1800404F2
0x180040231  mov     eax, [rdi+34h]
0x180040234  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x18004023b  mov     [rbp+Data], eax
0x18004023e  mov     r9d, r14d; dwType
0x180040241  lea     rax, [rbp+Data]
0x180040245  mov     [rsp+30h+cbData], r14d; cbData
0x18004024a  xor     r8d, r8d; Reserved
0x18004024d  mov     [rsp+30h+lpData], rax; lpData
0x180040252  mov     rcx, rsi; hKey
0x180040255  call    cs:__imp_RegSetValueExW
0x18004025b  mov     ebx, eax
0x18004025d  test    eax, eax
0x18004025f  jnz     loc_1800404F2
0x180040265  mov     eax, [rdi+38h]
0x180040268  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x18004026f  mov     [rbp+Data], eax
0x180040272  mov     r9d, r14d; dwType
0x180040275  lea     rax, [rbp+Data]
0x180040279  mov     [rsp+30h+cbData], r14d; cbData
0x18004027e  xor     r8d, r8d; Reserved
0x180040281  mov     [rsp+30h+lpData], rax; lpData
0x180040286  mov     rcx, rsi; hKey
0x180040289  call    cs:__imp_RegSetValueExW
0x18004028f  mov     ebx, eax
0x180040291  test    eax, eax
0x180040293  jnz     loc_1800404F2
0x180040299  mov     eax, [rdi+3Ch]
0x18004029c  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x1800402a3  mov     [rbp+Data], eax
0x1800402a6  mov     r9d, r14d; dwType
0x1800402a9  lea     rax, [rbp+Data]
0x1800402ad  mov     [rsp+30h+cbData], r14d; cbData
0x1800402b2  xor     r8d, r8d; Reserved
0x1800402b5  mov     [rsp+30h+lpData], rax; lpData
0x1800402ba  mov     rcx, rsi; hKey
0x1800402bd  call    cs:__imp_RegSetValueExW
0x1800402c3  mov     ebx, eax
0x1800402c5  test    eax, eax
0x1800402c7  jnz     loc_1800404F2
0x1800402cd  mov     eax, [rdi+40h]
0x1800402d0  lea     rdx, aCallbackmode; "CallbackMode"
0x1800402d7  mov     [rbp+Data], eax
0x1800402da  mov     r9d, r14d; dwType
0x1800402dd  lea     rax, [rbp+Data]
0x1800402e1  mov     [rsp+30h+cbData], r14d; cbData
0x1800402e6  xor     r8d, r8d; Reserved
0x1800402e9  mov     [rsp+30h+lpData], rax; lpData
0x1800402ee  mov     rcx, rsi; hKey
0x1800402f1  call    cs:__imp_RegSetValueExW
0x1800402f7  mov     ebx, eax
0x1800402f9  test    eax, eax
0x1800402fb  jnz     loc_1800404F2
0x180040301  mov     eax, [rdi+58h]
0x180040304  lea     rdx, aPhonebookmode; "PhonebookMode"
0x18004030b  mov     [rbp+Data], eax
0x18004030e  mov     r9d, r14d; dwType
0x180040311  lea     rax, [rbp+Data]
0x180040315  mov     [rsp+30h+cbData], r14d; cbData
0x18004031a  xor     r8d, r8d; Reserved
0x18004031d  mov     [rsp+30h+lpData], rax; lpData
0x180040322  mov     rcx, rsi; hKey
0x180040325  call    cs:__imp_RegSetValueExW
0x18004032b  mov     ebx, eax
0x18004032d  test    eax, eax
0x18004032f  jnz     loc_1800404F2
0x180040335  mov     eax, [rdi+80h]
0x18004033b  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x180040342  mov     [rbp+Data], eax
0x180040345  mov     r9d, r14d; dwType
0x180040348  lea     rax, [rbp+Data]
0x18004034c  mov     [rsp+30h+cbData], r14d; cbData
0x180040351  xor     r8d, r8d; Reserved
0x180040354  mov     [rsp+30h+lpData], rax; lpData
0x180040359  mov     rcx, rsi; hKey
0x18004035c  call    cs:__imp_RegSetValueExW
0x180040362  mov     ebx, eax
0x180040364  test    eax, eax
0x180040366  jnz     loc_1800404F2
0x18004036c  mov     eax, [rdi+0A0h]
0x180040372  lea     rdx, aWindowx; "WindowX"
0x180040379  mov     [rbp+Data], eax
0x18004037c  mov     r9d, r14d; dwType
0x18004037f  lea     rax, [rbp+Data]
0x180040383  mov     [rsp+30h+cbData], r14d; cbData
0x180040388  xor     r8d, r8d; Reserved
0x18004038b  mov     [rsp+30h+lpData], rax; lpData
0x180040390  mov     rcx, rsi; hKey
0x180040393  call    cs:__imp_RegSetValueExW
0x180040399  mov     ebx, eax
0x18004039b  test    eax, eax
0x18004039d  jnz     loc_1800404F2
0x1800403a3  mov     eax, [rdi+0A4h]
0x1800403a9  lea     rdx, aWindowy; "WindowY"
0x1800403b0  mov     [rbp+Data], eax
0x1800403b3  mov     r9d, r14d; dwType
0x1800403b6  lea     rax, [rbp+Data]
0x1800403ba  mov     [rsp+30h+cbData], r14d; cbData
0x1800403bf  xor     r8d, r8d; Reserved
0x1800403c2  mov     [rsp+30h+lpData], rax; lpData
0x1800403c7  mov     rcx, rsi; hKey
0x1800403ca  call    cs:__imp_RegSetValueExW
0x1800403d0  mov     rdx, [rdi+48h]
0x1800403d4  mov     rcx, rsi
0x1800403d7  call    SetCallbackList
0x1800403dc  mov     ebx, eax
0x1800403de  test    eax, eax
0x1800403e0  jnz     loc_1800404F2
0x1800403e6  mov     r8, [rdi+70h]
0x1800403ea  lea     rdx, aPhonebooks; "Phonebooks"
0x1800403f1  mov     rcx, rsi; hKey
0x1800403f4  call    SetRegMultiSz
0x1800403f9  mov     ebx, eax
0x1800403fb  test    eax, eax
0x1800403fd  jnz     loc_1800404F2
0x180040403  mov     r8, [rdi+78h]
  ... truncated ...
```
