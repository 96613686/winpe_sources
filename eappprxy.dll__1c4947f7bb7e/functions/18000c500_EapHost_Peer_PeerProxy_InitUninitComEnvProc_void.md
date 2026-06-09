# EapHost::Peer::PeerProxy::InitUninitComEnvProc(void *)

- ea: `0x18000c500`
- end: `0x18000c6d9`
- name: `?InitUninitComEnvProc@PeerProxy@Peer@EapHost@@CAIPEAX@Z`
- size: `473`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001780`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000ade4`
- `0x18000c500`
- `0x18000d1dc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c59d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c59d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c66a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c66a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c648`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c648`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c562`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c562`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c678`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c678`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::PeerProxy::InitUninitComEnvProc(unsigned int *a1)
{
  DWORD v2; // edi
  void *v3; // rsi
  HRESULT v4; // eax
  __int64 v5; // r8
  __int64 v6; // rax
  _BYTE v8[16]; // [rsp+40h] [rbp-858h] BYREF
  const char *v9; // [rsp+50h] [rbp-848h]
  __int64 v10; // [rsp+58h] [rbp-840h]
  WCHAR *v11; // [rsp+60h] [rbp-838h]
  int v12; // [rsp+68h] [rbp-830h]
  int v13; // [rsp+6Ch] [rbp-82Ch]
  WCHAR Buffer[1024]; // [rsp+70h] [rbp-828h] BYREF

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids);
  v3 = (void *)*((_QWORD *)a1 + 10);
  v4 = CoInitializeEx(0, 0);
  a1[28] = v4;
  if ( v4 < 0 )
  {
    FormatMessageW(0x1200u, 0, v4, 0, Buffer, 0x400u, 0);
    if ( (Microsoft_Windows_EapHostEnableBits & 0x10) != 0 )
    {
      v10 = 17;
      v9 = "CoInitializeEx()";
      v6 = -1;
      do
        ++v6;
      while ( Buffer[v6] );
      v13 = 0;
      v12 = 2 * v6 + 2;
      v11 = Buffer;
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)PeerCOMAPIFailure, v5, 3, (__int64)v8);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, a1[28]);
    v2 = *((unsigned __int16 *)a1 + 56);
  }
  SetEvent(*((HANDLE *)a1 + 8));
  if ( (a1[28] & 0x80000000) == 0 )
  {
    v2 = WaitForSingleObject(v3, 0xFFFFFFFF);
    CoUninitialize();
  }
  else
  {
    ObjectHandle::Clear((ObjectHandle *)(a1 + 22));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18000c500  mov     [rsp+arg_8], rbx
0x18000c505  mov     [rsp+arg_10], rbp
0x18000c50a  push    rsi
0x18000c50b  push    rdi
0x18000c50c  push    r14
0x18000c50e  sub     rsp, 880h
0x18000c515  mov     rax, cs:__security_cookie
0x18000c51c  xor     rax, rsp
0x18000c51f  mov     [rsp+898h+var_28], rax
0x18000c527  xor     ebp, ebp
0x18000c529  mov     rbx, rcx
0x18000c52c  mov     edi, ebp
0x18000c52e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c535  lea     r14, WPP_GLOBAL_Control
0x18000c53c  cmp     rcx, r14
0x18000c53f  jz      short loc_18000C55A
0x18000c541  test    byte ptr [rcx+1Ch], 4
0x18000c545  jz      short loc_18000C55A
0x18000c547  mov     rcx, [rcx+10h]
0x18000c54b  lea     edx, [rbp+1Bh]
0x18000c54e  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c555  call    WPP_SF_
0x18000c55a  mov     rsi, [rbx+50h]
0x18000c55e  xor     edx, edx; dwCoInit
0x18000c560  xor     ecx, ecx; pvReserved
0x18000c562  call    cs:__imp_CoInitializeEx
0x18000c569  nop     dword ptr [rax+rax+00h]
0x18000c56e  mov     [rbx+70h], eax
0x18000c571  test    eax, eax
0x18000c573  jns     loc_18000C644
0x18000c579  lea     rcx, [rsp+898h+Buffer]
0x18000c57e  mov     [rsp+898h+Arguments], rbp; Arguments
0x18000c583  mov     [rsp+898h+nSize], 400h; nSize
0x18000c58b  xor     r9d, r9d; dwLanguageId
0x18000c58e  mov     [rsp+898h+lpBuffer], rcx; lpBuffer
0x18000c593  mov     r8d, eax; dwMessageId
0x18000c596  mov     ecx, 1200h; dwFlags
0x18000c59b  xor     edx, edx; lpSource
0x18000c59d  call    cs:__imp_FormatMessageW
0x18000c5a4  nop     dword ptr [rax+rax+00h]
0x18000c5a9  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x18000c5b0  jz      short loc_18000C615
0x18000c5b2  lea     rax, aCoinitializeex_0; "CoInitializeEx()"
0x18000c5b9  mov     [rsp+898h+var_840], 11h
0x18000c5c2  mov     [rsp+898h+var_848], rax
0x18000c5c7  lea     rcx, [rsp+898h+Buffer]
0x18000c5cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c5d0  inc     rax
0x18000c5d3  cmp     [rcx+rax*2], bp
0x18000c5d7  jnz     short loc_18000C5D0
0x18000c5d9  lea     eax, ds:2[rax*2]
0x18000c5e0  mov     [rsp+898h+var_82C], ebp
0x18000c5e4  lea     rcx, [rsp+898h+Buffer]
0x18000c5e9  mov     [rsp+898h+var_830], eax
0x18000c5ed  lea     rax, [rsp+898h+var_858]
0x18000c5f2  mov     [rsp+898h+var_838], rcx
0x18000c5f7  mov     r9d, 3
0x18000c5fd  mov     [rsp+898h+lpBuffer], rax
0x18000c602  lea     rdx, PeerCOMAPIFailure
0x18000c609  lea     rcx, eaphost_Context
0x18000c610  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c615  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c61c  cmp     rcx, r14
0x18000c61f  jz      short loc_18000C640
0x18000c621  test    byte ptr [rcx+1Ch], 1
0x18000c625  jz      short loc_18000C640
0x18000c627  mov     r9d, [rbx+70h]
0x18000c62b  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c632  mov     rcx, [rcx+10h]
0x18000c636  mov     edx, 1Ch
0x18000c63b  call    WPP_SF_d
0x18000c640  movzx   edi, word ptr [rbx+70h]
0x18000c644  mov     rcx, [rbx+40h]; hEvent
0x18000c648  call    cs:__imp_SetEvent
0x18000c64f  nop     dword ptr [rax+rax+00h]
0x18000c654  cmp     [rbx+70h], ebp
0x18000c657  jge     short loc_18000C664
0x18000c659  lea     rcx, [rbx+58h]; this
0x18000c65d  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000c662  jmp     short loc_18000C684
0x18000c664  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c667  mov     rcx, rsi; hHandle
0x18000c66a  call    cs:__imp_WaitForSingleObject
0x18000c671  nop     dword ptr [rax+rax+00h]
0x18000c676  mov     edi, eax
0x18000c678  call    cs:__imp_CoUninitialize
0x18000c67f  nop     dword ptr [rax+rax+00h]
0x18000c684  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c68b  cmp     rcx, r14
0x18000c68e  jz      short loc_18000C6AE
0x18000c690  test    byte ptr [rcx+1Ch], 4
0x18000c694  jz      short loc_18000C6AE
0x18000c696  mov     rcx, [rcx+10h]
0x18000c69a  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c6a1  mov     edx, 1Dh
0x18000c6a6  mov     r9d, edi
0x18000c6a9  call    WPP_SF_d
0x18000c6ae  mov     eax, edi
0x18000c6b0  mov     rcx, [rsp+898h+var_28]
0x18000c6b8  xor     rcx, rsp; StackCookie
0x18000c6bb  call    __security_check_cookie
0x18000c6c0  lea     r11, [rsp+898h+var_18]
0x18000c6c8  mov     rbx, [r11+28h]
0x18000c6cc  mov     rbp, [r11+30h]
0x18000c6d0  mov     rsp, r11
0x18000c6d3  pop     r14
0x18000c6d5  pop     rdi
0x18000c6d6  pop     rsi
0x18000c6d7  retn
```
