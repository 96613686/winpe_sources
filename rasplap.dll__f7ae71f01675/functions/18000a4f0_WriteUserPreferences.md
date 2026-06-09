# WriteUserPreferences

- ea: `0x18000a4f0`
- end: `0x18000aac7`
- name: `WriteUserPreferences`
- size: `1495`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009464`

## callees

- `0x180009eac`
- `0x18000a2b0`
- `0x18000a4f0`
- `0x18000ae90`
- `0x18000afb4`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x18000a551`
- `KERNEL32!RegSetValueExW` at `0x18000a585`
- `KERNEL32!RegSetValueExW` at `0x18000a5b9`
- `KERNEL32!RegSetValueExW` at `0x18000a5ed`
- `KERNEL32!RegSetValueExW` at `0x18000a621`
- `KERNEL32!RegSetValueExW` at `0x18000a655`
- `KERNEL32!RegSetValueExW` at `0x18000a689`
- `KERNEL32!RegSetValueExW` at `0x18000a6bd`
- `KERNEL32!RegSetValueExW` at `0x18000a6f1`
- `KERNEL32!RegSetValueExW` at `0x18000a725`
- `KERNEL32!RegSetValueExW` at `0x18000a759`
- `KERNEL32!RegSetValueExW` at `0x18000a78d`
- `KERNEL32!RegSetValueExW` at `0x18000a7c1`
- `KERNEL32!RegSetValueExW` at `0x18000a7f5`
- `KERNEL32!RegSetValueExW` at `0x18000a829`
- `KERNEL32!RegSetValueExW` at `0x18000a85d`
- `KERNEL32!RegSetValueExW` at `0x18000a891`
- `KERNEL32!RegSetValueExW` at `0x18000a8c5`
- `KERNEL32!RegSetValueExW` at `0x18000a8fc`
- `KERNEL32!RegSetValueExW` at `0x18000a933`
- `KERNEL32!RegSetValueExW` at `0x18000a96a`
- `KERNEL32!RegSetValueExW` at `0x18000a551`
- `KERNEL32!RegSetValueExW` at `0x18000a585`
- `KERNEL32!RegSetValueExW` at `0x18000a5b9`
- `KERNEL32!RegSetValueExW` at `0x18000a5ed`
- `KERNEL32!RegSetValueExW` at `0x18000a621`
- `KERNEL32!RegSetValueExW` at `0x18000a655`
- `KERNEL32!RegSetValueExW` at `0x18000a689`
- `KERNEL32!RegSetValueExW` at `0x18000a6bd`
- `KERNEL32!RegSetValueExW` at `0x18000a6f1`
- `KERNEL32!RegSetValueExW` at `0x18000a725`
- `KERNEL32!RegSetValueExW` at `0x18000a759`
- `KERNEL32!RegSetValueExW` at `0x18000a78d`
- `KERNEL32!RegSetValueExW` at `0x18000a7c1`
- `KERNEL32!RegSetValueExW` at `0x18000a7f5`
- `KERNEL32!RegSetValueExW` at `0x18000a829`
- `KERNEL32!RegSetValueExW` at `0x18000a85d`
- `KERNEL32!RegSetValueExW` at `0x18000a891`
- `KERNEL32!RegSetValueExW` at `0x18000a8c5`
- `KERNEL32!RegSetValueExW` at `0x18000a8fc`
- `KERNEL32!RegSetValueExW` at `0x18000a933`
- `KERNEL32!RegSetValueExW` at `0x18000a96a`
- `KERNEL32!RegDeleteValueW` at `0x18000aa86`
- `KERNEL32!RegDeleteValueW` at `0x18000aa86`
- `rtutils!TracePrintfExA` at `0x18000a522`
- `rtutils!TracePrintfExA` at `0x18000aaac`
- `rtutils!TracePrintfExA` at `0x18000a522`
- `rtutils!TracePrintfExA` at `0x18000aaac`

## string_xrefs

- `0x18000a704`: `SkipConnectComplete`
- `0x18000a738`: `RedialAttempts`
- `0x18000a7d4`: `RedialOnLinkFailure`
- `0x18000aa7c`: `PersonalPhonebookPath`
- `0x18000aa4b`: `AlternatePhonebookPath`
- `0x18000a516`: `WriteUserPreferences`
- `0x18000aaa0`: `WriteUserPreferences=%d`

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
0x18000a4f0  mov     [rsp-18h+arg_0], rbx
0x18000a4f5  mov     [rsp-18h+arg_10], rsi
0x18000a4fa  push    rbp
0x18000a4fb  push    rdi
0x18000a4fc  push    r14
0x18000a4fe  mov     rbp, rsp
0x18000a501  sub     rsp, 30h
0x18000a505  mov     rsi, rcx
0x18000a508  mov     rdi, rdx
0x18000a50b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a511  cmp     ecx, 0FFFFFFFFh
0x18000a514  jz      short loc_18000A528
0x18000a516  lea     r8, aWriteuserprefe; "WriteUserPreferences"
0x18000a51d  mov     edx, 0Ch; dwFlags
0x18000a522  call    cs:__imp_TracePrintfExA
0x18000a528  mov     eax, [rdi]
0x18000a52a  lea     rdx, aOperatordial; "OperatorDial"
0x18000a531  mov     [rbp+Data], eax
0x18000a534  mov     r14d, 4
0x18000a53a  lea     rax, [rbp+Data]
0x18000a53e  mov     [rsp+30h+cbData], r14d; cbData
0x18000a543  mov     r9d, r14d; dwType
0x18000a546  mov     [rsp+30h+lpData], rax; lpData
0x18000a54b  xor     r8d, r8d; Reserved
0x18000a54e  mov     rcx, rsi; hKey
0x18000a551  call    cs:__imp_RegSetValueExW
0x18000a557  mov     ebx, eax
0x18000a559  test    eax, eax
0x18000a55b  jnz     loc_18000AA92
0x18000a561  mov     eax, [rdi+4]
0x18000a564  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x18000a56b  mov     [rbp+Data], eax
0x18000a56e  mov     r9d, r14d; dwType
0x18000a571  lea     rax, [rbp+Data]
0x18000a575  mov     [rsp+30h+cbData], r14d; cbData
0x18000a57a  xor     r8d, r8d; Reserved
0x18000a57d  mov     [rsp+30h+lpData], rax; lpData
0x18000a582  mov     rcx, rsi; hKey
0x18000a585  call    cs:__imp_RegSetValueExW
0x18000a58b  mov     ebx, eax
0x18000a58d  test    eax, eax
0x18000a58f  jnz     loc_18000AA92
0x18000a595  mov     eax, [rdi+8]
0x18000a598  lea     rdx, aUselocation; "UseLocation"
0x18000a59f  mov     [rbp+Data], eax
0x18000a5a2  mov     r9d, r14d; dwType
0x18000a5a5  lea     rax, [rbp+Data]
0x18000a5a9  mov     [rsp+30h+cbData], r14d; cbData
0x18000a5ae  xor     r8d, r8d; Reserved
0x18000a5b1  mov     [rsp+30h+lpData], rax; lpData
0x18000a5b6  mov     rcx, rsi; hKey
0x18000a5b9  call    cs:__imp_RegSetValueExW
0x18000a5bf  mov     ebx, eax
0x18000a5c1  test    eax, eax
0x18000a5c3  jnz     loc_18000AA92
0x18000a5c9  mov     eax, [rdi+0Ch]
0x18000a5cc  lea     rdx, aShowlights; "ShowLights"
0x18000a5d3  mov     [rbp+Data], eax
0x18000a5d6  mov     r9d, r14d; dwType
0x18000a5d9  lea     rax, [rbp+Data]
0x18000a5dd  mov     [rsp+30h+cbData], r14d; cbData
0x18000a5e2  xor     r8d, r8d; Reserved
0x18000a5e5  mov     [rsp+30h+lpData], rax; lpData
0x18000a5ea  mov     rcx, rsi; hKey
0x18000a5ed  call    cs:__imp_RegSetValueExW
0x18000a5f3  mov     ebx, eax
0x18000a5f5  test    eax, eax
0x18000a5f7  jnz     loc_18000AA92
0x18000a5fd  mov     eax, [rdi+10h]
0x18000a600  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x18000a607  mov     [rbp+Data], eax
0x18000a60a  mov     r9d, r14d; dwType
0x18000a60d  lea     rax, [rbp+Data]
0x18000a611  mov     [rsp+30h+cbData], r14d; cbData
0x18000a616  xor     r8d, r8d; Reserved
0x18000a619  mov     [rsp+30h+lpData], rax; lpData
0x18000a61e  mov     rcx, rsi; hKey
0x18000a621  call    cs:__imp_RegSetValueExW
0x18000a627  mov     ebx, eax
0x18000a629  test    eax, eax
0x18000a62b  jnz     loc_18000AA92
0x18000a631  mov     eax, [rdi+24h]
0x18000a634  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x18000a63b  mov     [rbp+Data], eax
0x18000a63e  mov     r9d, r14d; dwType
0x18000a641  lea     rax, [rbp+Data]
0x18000a645  mov     [rsp+30h+cbData], r14d; cbData
0x18000a64a  xor     r8d, r8d; Reserved
0x18000a64d  mov     [rsp+30h+lpData], rax; lpData
0x18000a652  mov     rcx, rsi; hKey
0x18000a655  call    cs:__imp_RegSetValueExW
0x18000a65b  mov     ebx, eax
0x18000a65d  test    eax, eax
0x18000a65f  jnz     loc_18000AA92
0x18000a665  mov     eax, [rdi+14h]
0x18000a668  lea     rdx, aCloseondial; "CloseOnDial"
0x18000a66f  mov     [rbp+Data], eax
0x18000a672  mov     r9d, r14d; dwType
0x18000a675  lea     rax, [rbp+Data]
0x18000a679  mov     [rsp+30h+cbData], r14d; cbData
0x18000a67e  xor     r8d, r8d; Reserved
0x18000a681  mov     [rsp+30h+lpData], rax; lpData
0x18000a686  mov     rcx, rsi; hKey
0x18000a689  call    cs:__imp_RegSetValueExW
0x18000a68f  mov     ebx, eax
0x18000a691  test    eax, eax
0x18000a693  jnz     loc_18000AA92
0x18000a699  mov     eax, [rdi+18h]
0x18000a69c  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x18000a6a3  mov     [rbp+Data], eax
0x18000a6a6  mov     r9d, r14d; dwType
0x18000a6a9  lea     rax, [rbp+Data]
0x18000a6ad  mov     [rsp+30h+cbData], r14d; cbData
0x18000a6b2  xor     r8d, r8d; Reserved
0x18000a6b5  mov     [rsp+30h+lpData], rax; lpData
0x18000a6ba  mov     rcx, rsi; hKey
0x18000a6bd  call    cs:__imp_RegSetValueExW
0x18000a6c3  mov     ebx, eax
0x18000a6c5  test    eax, eax
0x18000a6c7  jnz     loc_18000AA92
0x18000a6cd  mov     eax, [rdi+1Ch]
0x18000a6d0  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x18000a6d7  mov     [rbp+Data], eax
0x18000a6da  mov     r9d, r14d; dwType
0x18000a6dd  lea     rax, [rbp+Data]
0x18000a6e1  mov     [rsp+30h+cbData], r14d; cbData
0x18000a6e6  xor     r8d, r8d; Reserved
0x18000a6e9  mov     [rsp+30h+lpData], rax; lpData
0x18000a6ee  mov     rcx, rsi; hKey
0x18000a6f1  call    cs:__imp_RegSetValueExW
0x18000a6f7  mov     ebx, eax
0x18000a6f9  test    eax, eax
0x18000a6fb  jnz     loc_18000AA92
0x18000a701  mov     eax, [rdi+20h]
0x18000a704  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x18000a70b  mov     [rbp+Data], eax
0x18000a70e  mov     r9d, r14d; dwType
0x18000a711  lea     rax, [rbp+Data]
0x18000a715  mov     [rsp+30h+cbData], r14d; cbData
0x18000a71a  xor     r8d, r8d; Reserved
0x18000a71d  mov     [rsp+30h+lpData], rax; lpData
0x18000a722  mov     rcx, rsi; hKey
0x18000a725  call    cs:__imp_RegSetValueExW
0x18000a72b  mov     ebx, eax
0x18000a72d  test    eax, eax
0x18000a72f  jnz     loc_18000AA92
0x18000a735  mov     eax, [rdi+28h]
0x18000a738  lea     rdx, aRedialattempts; "RedialAttempts"
0x18000a73f  mov     [rbp+Data], eax
0x18000a742  mov     r9d, r14d; dwType
0x18000a745  lea     rax, [rbp+Data]
0x18000a749  mov     [rsp+30h+cbData], r14d; cbData
0x18000a74e  xor     r8d, r8d; Reserved
0x18000a751  mov     [rsp+30h+lpData], rax; lpData
0x18000a756  mov     rcx, rsi; hKey
0x18000a759  call    cs:__imp_RegSetValueExW
0x18000a75f  mov     ebx, eax
0x18000a761  test    eax, eax
0x18000a763  jnz     loc_18000AA92
0x18000a769  mov     eax, [rdi+2Ch]
0x18000a76c  lea     rdx, aRedialseconds; "RedialSeconds"
0x18000a773  mov     [rbp+Data], eax
0x18000a776  mov     r9d, r14d; dwType
0x18000a779  lea     rax, [rbp+Data]
0x18000a77d  mov     [rsp+30h+cbData], r14d; cbData
0x18000a782  xor     r8d, r8d; Reserved
0x18000a785  mov     [rsp+30h+lpData], rax; lpData
0x18000a78a  mov     rcx, rsi; hKey
0x18000a78d  call    cs:__imp_RegSetValueExW
0x18000a793  mov     ebx, eax
0x18000a795  test    eax, eax
0x18000a797  jnz     loc_18000AA92
0x18000a79d  mov     eax, [rdi+30h]
0x18000a7a0  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x18000a7a7  mov     [rbp+Data], eax
0x18000a7aa  mov     r9d, r14d; dwType
0x18000a7ad  lea     rax, [rbp+Data]
0x18000a7b1  mov     [rsp+30h+cbData], r14d; cbData
0x18000a7b6  xor     r8d, r8d; Reserved
0x18000a7b9  mov     [rsp+30h+lpData], rax; lpData
0x18000a7be  mov     rcx, rsi; hKey
0x18000a7c1  call    cs:__imp_RegSetValueExW
0x18000a7c7  mov     ebx, eax
0x18000a7c9  test    eax, eax
0x18000a7cb  jnz     loc_18000AA92
0x18000a7d1  mov     eax, [rdi+34h]
0x18000a7d4  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x18000a7db  mov     [rbp+Data], eax
0x18000a7de  mov     r9d, r14d; dwType
0x18000a7e1  lea     rax, [rbp+Data]
0x18000a7e5  mov     [rsp+30h+cbData], r14d; cbData
0x18000a7ea  xor     r8d, r8d; Reserved
0x18000a7ed  mov     [rsp+30h+lpData], rax; lpData
0x18000a7f2  mov     rcx, rsi; hKey
0x18000a7f5  call    cs:__imp_RegSetValueExW
0x18000a7fb  mov     ebx, eax
0x18000a7fd  test    eax, eax
0x18000a7ff  jnz     loc_18000AA92
0x18000a805  mov     eax, [rdi+38h]
0x18000a808  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x18000a80f  mov     [rbp+Data], eax
0x18000a812  mov     r9d, r14d; dwType
0x18000a815  lea     rax, [rbp+Data]
0x18000a819  mov     [rsp+30h+cbData], r14d; cbData
0x18000a81e  xor     r8d, r8d; Reserved
0x18000a821  mov     [rsp+30h+lpData], rax; lpData
0x18000a826  mov     rcx, rsi; hKey
0x18000a829  call    cs:__imp_RegSetValueExW
0x18000a82f  mov     ebx, eax
0x18000a831  test    eax, eax
0x18000a833  jnz     loc_18000AA92
0x18000a839  mov     eax, [rdi+3Ch]
0x18000a83c  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x18000a843  mov     [rbp+Data], eax
0x18000a846  mov     r9d, r14d; dwType
0x18000a849  lea     rax, [rbp+Data]
0x18000a84d  mov     [rsp+30h+cbData], r14d; cbData
0x18000a852  xor     r8d, r8d; Reserved
0x18000a855  mov     [rsp+30h+lpData], rax; lpData
0x18000a85a  mov     rcx, rsi; hKey
0x18000a85d  call    cs:__imp_RegSetValueExW
0x18000a863  mov     ebx, eax
0x18000a865  test    eax, eax
0x18000a867  jnz     loc_18000AA92
0x18000a86d  mov     eax, [rdi+40h]
0x18000a870  lea     rdx, aCallbackmode; "CallbackMode"
0x18000a877  mov     [rbp+Data], eax
0x18000a87a  mov     r9d, r14d; dwType
0x18000a87d  lea     rax, [rbp+Data]
0x18000a881  mov     [rsp+30h+cbData], r14d; cbData
0x18000a886  xor     r8d, r8d; Reserved
0x18000a889  mov     [rsp+30h+lpData], rax; lpData
0x18000a88e  mov     rcx, rsi; hKey
0x18000a891  call    cs:__imp_RegSetValueExW
0x18000a897  mov     ebx, eax
0x18000a899  test    eax, eax
0x18000a89b  jnz     loc_18000AA92
0x18000a8a1  mov     eax, [rdi+58h]
0x18000a8a4  lea     rdx, aPhonebookmode; "PhonebookMode"
0x18000a8ab  mov     [rbp+Data], eax
0x18000a8ae  mov     r9d, r14d; dwType
0x18000a8b1  lea     rax, [rbp+Data]
0x18000a8b5  mov     [rsp+30h+cbData], r14d; cbData
0x18000a8ba  xor     r8d, r8d; Reserved
0x18000a8bd  mov     [rsp+30h+lpData], rax; lpData
0x18000a8c2  mov     rcx, rsi; hKey
0x18000a8c5  call    cs:__imp_RegSetValueExW
0x18000a8cb  mov     ebx, eax
0x18000a8cd  test    eax, eax
0x18000a8cf  jnz     loc_18000AA92
0x18000a8d5  mov     eax, [rdi+80h]
0x18000a8db  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x18000a8e2  mov     [rbp+Data], eax
0x18000a8e5  mov     r9d, r14d; dwType
0x18000a8e8  lea     rax, [rbp+Data]
0x18000a8ec  mov     [rsp+30h+cbData], r14d; cbData
0x18000a8f1  xor     r8d, r8d; Reserved
0x18000a8f4  mov     [rsp+30h+lpData], rax; lpData
0x18000a8f9  mov     rcx, rsi; hKey
0x18000a8fc  call    cs:__imp_RegSetValueExW
0x18000a902  mov     ebx, eax
0x18000a904  test    eax, eax
0x18000a906  jnz     loc_18000AA92
0x18000a90c  mov     eax, [rdi+0A0h]
0x18000a912  lea     rdx, aWindowx; "WindowX"
0x18000a919  mov     [rbp+Data], eax
0x18000a91c  mov     r9d, r14d; dwType
0x18000a91f  lea     rax, [rbp+Data]
0x18000a923  mov     [rsp+30h+cbData], r14d; cbData
0x18000a928  xor     r8d, r8d; Reserved
0x18000a92b  mov     [rsp+30h+lpData], rax; lpData
0x18000a930  mov     rcx, rsi; hKey
0x18000a933  call    cs:__imp_RegSetValueExW
0x18000a939  mov     ebx, eax
0x18000a93b  test    eax, eax
0x18000a93d  jnz     loc_18000AA92
0x18000a943  mov     eax, [rdi+0A4h]
0x18000a949  lea     rdx, aWindowy; "WindowY"
0x18000a950  mov     [rbp+Data], eax
0x18000a953  mov     r9d, r14d; dwType
0x18000a956  lea     rax, [rbp+Data]
0x18000a95a  mov     [rsp+30h+cbData], r14d; cbData
0x18000a95f  xor     r8d, r8d; Reserved
0x18000a962  mov     [rsp+30h+lpData], rax; lpData
0x18000a967  mov     rcx, rsi; hKey
0x18000a96a  call    cs:__imp_RegSetValueExW
0x18000a970  mov     rdx, [rdi+48h]
0x18000a974  mov     rcx, rsi
0x18000a977  call    SetCallbackList
0x18000a97c  mov     ebx, eax
0x18000a97e  test    eax, eax
0x18000a980  jnz     loc_18000AA92
0x18000a986  mov     r8, [rdi+70h]
0x18000a98a  lea     rdx, aPhonebooks; "Phonebooks"
0x18000a991  mov     rcx, rsi; hKey
0x18000a994  call    SetRegMultiSz
0x18000a999  mov     ebx, eax
0x18000a99b  test    eax, eax
0x18000a99d  jnz     loc_18000AA92
0x18000a9a3  mov     r8, [rdi+78h]
  ... truncated ...
```
