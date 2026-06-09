# DpspSendClientFeedback

- ea: `0x180001100`
- end: `0x180001394`
- name: `DpspSendClientFeedback`
- size: `660`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180002090`
- `0x180003830`
- `0x180004de4`

## callees

- `0x180001100`
- `0x1800013a0`
- `0x180009090`
- `0x1800099bc`
- `0x18000a856`
- `0x180011b88`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180001192`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180001192`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000135d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000135d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000134f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000134f`

## pseudocode

```c
__int64 __fastcall DpspSendClientFeedback(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v3; // rbx
  int v4; // ebp
  int v5; // r12d
  unsigned int v7; // esi
  unsigned int v8; // r15d
  _DWORD *v9; // rax
  BOOL v10; // ecx
  _OWORD *v11; // rdx
  int Args; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax

  v3 = 0;
  v4 = a2;
  v5 = a3;
  if ( a1 )
  {
    v7 = 0;
    *(_DWORD *)(a1 + 200) = a2;
    if ( *(_QWORD *)(a1 + 792) && (*(_DWORD *)(a1 + 104) & 4) == 0 )
    {
      v8 = **(_DWORD **)(a1 + 1224) + 256;
      if ( v8 > (unsigned __int64)AlpcMaxAllowedMessageLength(a1, a2, a3) || v8 < 0xF8 )
      {
        v7 = -2147024774;
      }
      else
      {
        v9 = (_DWORD *)WdipAlloc(v8);
        v3 = v9;
        if ( v9 )
        {
          memset_0(v9, 0, v8);
          switch ( v4 )
          {
            case 0:
              v3[11] = 11;
              v10 = 1;
              goto LABEL_21;
            case 1:
              v3[11] = 12;
              if ( v3 != (_DWORD *)-128LL && a1 != -40 )
                *((_OWORD *)v3 + 8) = *(_OWORD *)(a1 + 40);
              v10 = 1;
              goto LABEL_21;
            case 2:
              v3[11] = 14;
              v10 = (*(_BYTE *)(a1 + 92) & 0xF) != 0;
              goto LABEL_21;
            case 3:
              v3[11] = 13;
              goto LABEL_20;
            case 4:
              v3[11] = 15;
              goto LABEL_20;
            case 5:
              v3[11] = 21;
              goto LABEL_20;
            case 6:
              v3[11] = 22;
LABEL_20:
              v10 = 0;
LABEL_21:
              v3[28] = v5;
              if ( v3 != (_DWORD *)-64LL && a1 != -24 )
                *((_OWORD *)v3 + 4) = *(_OWORD *)(a1 + 24);
              if ( v3 != (_DWORD *)-96LL && a1 != -56 )
                *((_OWORD *)v3 + 6) = *(_OWORD *)(a1 + 56);
              if ( v3 != (_DWORD *)-48LL )
              {
                v11 = *(_OWORD **)(a1 + 1216);
                if ( v11 )
                  *((_OWORD *)v3 + 3) = *v11;
              }
              v3[29] = *(_DWORD *)(a1 + 84);
              v3[31] = 208;
              if ( v10
                && (Args = WdipWriteParameterCollectionToMessageBuffer(*(_QWORD *)(a1 + 1224), v3, v8),
                    v7 = Args,
                    Args < 0) )
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
                  (int)L"DpspSendClientFeedback",
                  935,
                  (int)L"Error = %d",
                  Args);
              }
              else
              {
                v13 = DpspSendASyncMessage((struct _DPS_MESSAGE *)v3, 0, 0x10000u, *(void **)(a1 + 792), v8);
                v7 = v13;
                if ( v13 < 0 )
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
                    (int)L"DpspSendClientFeedback",
                    945,
                    (int)L"Error = %d",
                    v13);
              }
              break;
            default:
              break;
          }
        }
        else
        {
          v7 = -2147024882;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
            (int)L"DpspSendClientFeedback",
            858,
            (int)L"Error = %d",
            14);
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
      (int)L"DpspSendClientFeedback",
      837,
      (int)L"Error = %d",
      87);
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v3);
  return v7;
}

```

## disassembly

```asm
0x180001100  mov     [rsp+arg_10], rbx
0x180001105  mov     [rsp+arg_18], rbp
0x18000110a  push    rsi
0x18000110b  push    rdi
0x18000110c  push    r12
0x18000110e  sub     rsp, 30h
0x180001112  xor     ebx, ebx
0x180001114  movsxd  rbp, edx
0x180001117  mov     r12d, r8d
0x18000111a  mov     rdi, rcx
0x18000111d  test    rcx, rcx
0x180001120  jnz     short loc_180001154
0x180001122  lea     r9, aErrorD; "Error = %d"
0x180001129  mov     dword ptr [rsp+48h+Args], 57h ; 'W'; Args
0x180001131  mov     r8d, 345h; int
0x180001137  lea     rdx, aDpspsendclient; "DpspSendClientFeedback"
0x18000113e  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001145  mov     esi, 80070057h
0x18000114a  call    WdipTraceError
0x18000114f  jmp     loc_18000134F
0x180001154  xor     esi, esi
0x180001156  mov     [rcx+0C8h], ebp
0x18000115c  cmp     [rcx+318h], rbx
0x180001163  jz      loc_18000134F
0x180001169  mov     eax, [rcx+68h]
0x18000116c  test    al, 4
0x18000116e  jnz     loc_18000134F
0x180001174  mov     rax, [rcx+4C8h]
0x18000117b  mov     [rsp+48h+arg_0], r14
0x180001180  mov     [rsp+48h+arg_8], r15
0x180001185  mov     r15d, [rax]
0x180001188  add     r15d, 100h
0x18000118f  mov     r14d, r15d
0x180001192  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180001198  cmp     r14, rax
0x18000119b  ja      loc_180001340
0x1800011a1  cmp     r15d, 0F8h
0x1800011a8  jb      loc_180001340
0x1800011ae  mov     ecx, r14d
0x1800011b1  call    WdipAlloc
0x1800011b6  mov     rbx, rax
0x1800011b9  test    rax, rax
0x1800011bc  jnz     short loc_1800011D6
0x1800011be  mov     esi, 8007000Eh
0x1800011c3  mov     dword ptr [rsp+48h+Args], 0Eh
0x1800011cb  mov     r8d, 35Ah
0x1800011d1  jmp     loc_180001324
0x1800011d6  mov     r8, r14; Size
0x1800011d9  xor     edx, edx; Val
0x1800011db  mov     rcx, rbx; void *
0x1800011de  call    memset_0
0x1800011e3  cmp     ebp, 6; switch 7 cases
0x1800011e6  ja      def_1800011FD; jumptable 00000001800011FD default case
0x1800011ec  lea     rdx, __ImageBase
0x1800011f3  mov     ecx, ds:(jpt_1800011FD - 180000000h)[rdx+rbp*4]
0x1800011fa  add     rcx, rdx
0x1800011fd  jmp     rcx; switch jump
0x1800011ff  mov     dword ptr [rbx+2Ch], 0Bh; jumptable 00000001800011FD case 0
0x180001206  mov     ecx, 1
0x18000120b  jmp     short loc_18000126C
0x18000120d  mov     dword ptr [rbx+2Ch], 0Fh; jumptable 00000001800011FD case 4
0x180001214  jmp     short loc_18000126A
0x180001216  lea     rax, [rbx+80h]; jumptable 00000001800011FD case 1
0x18000121d  mov     dword ptr [rbx+2Ch], 0Ch
0x180001224  test    rax, rax
0x180001227  jz      short loc_180001238
0x180001229  lea     rcx, [rdi+28h]
0x18000122d  test    rcx, rcx
0x180001230  jz      short loc_180001238
0x180001232  movups  xmm0, xmmword ptr [rcx]
0x180001235  movups  xmmword ptr [rax], xmm0
0x180001238  mov     ecx, 1
0x18000123d  jmp     short loc_18000126C
0x18000123f  mov     dword ptr [rbx+2Ch], 0Dh; jumptable 00000001800011FD case 3
0x180001246  jmp     short loc_18000126A
0x180001248  mov     dword ptr [rbx+2Ch], 0Eh; jumptable 00000001800011FD case 2
0x18000124f  mov     ecx, esi
0x180001251  test    byte ptr [rdi+5Ch], 0Fh
0x180001255  setnz   cl
0x180001258  jmp     short loc_18000126C
0x18000125a  mov     dword ptr [rbx+2Ch], 15h; jumptable 00000001800011FD case 5
0x180001261  jmp     short loc_18000126A
0x180001263  mov     dword ptr [rbx+2Ch], 16h; jumptable 00000001800011FD case 6
0x18000126a  xor     ecx, ecx
0x18000126c  lea     rdx, [rbx+40h]
0x180001270  mov     [rbx+70h], r12d
0x180001274  test    rdx, rdx
0x180001277  jz      short loc_180001288
0x180001279  lea     rax, [rdi+18h]
0x18000127d  test    rax, rax
0x180001280  jz      short loc_180001288
0x180001282  movups  xmm0, xmmword ptr [rax]
0x180001285  movups  xmmword ptr [rdx], xmm0
0x180001288  lea     rax, [rbx+60h]
0x18000128c  test    rax, rax
0x18000128f  jz      short loc_1800012A0
0x180001291  lea     rdx, [rdi+38h]
0x180001295  test    rdx, rdx
0x180001298  jz      short loc_1800012A0
0x18000129a  movups  xmm0, xmmword ptr [rdx]
0x18000129d  movups  xmmword ptr [rax], xmm0
0x1800012a0  lea     rax, [rbx+30h]
0x1800012a4  test    rax, rax
0x1800012a7  jz      short loc_1800012BB
0x1800012a9  mov     rdx, [rdi+4C0h]
0x1800012b0  test    rdx, rdx
0x1800012b3  jz      short loc_1800012BB
0x1800012b5  movups  xmm0, xmmword ptr [rdx]
0x1800012b8  movups  xmmword ptr [rax], xmm0
0x1800012bb  mov     eax, [rdi+54h]
0x1800012be  mov     [rbx+74h], eax
0x1800012c1  mov     dword ptr [rbx+7Ch], 0D0h
0x1800012c8  cmp     ecx, 1
0x1800012cb  jnz     short loc_1800012F4
0x1800012cd  mov     rcx, [rdi+4C8h]
0x1800012d4  mov     r8d, r15d
0x1800012d7  mov     rdx, rbx
0x1800012da  call    WdipWriteParameterCollectionToMessageBuffer
0x1800012df  mov     esi, eax
0x1800012e1  test    eax, eax
0x1800012e3  jns     short loc_1800012F4
0x1800012e5  movzx   ecx, ax
0x1800012e8  mov     r8d, 3A7h
0x1800012ee  mov     dword ptr [rsp+48h+Args], ecx
0x1800012f2  jmp     short loc_180001324
0x1800012f4  mov     r9, [rdi+318h]; void *
0x1800012fb  xor     edx, edx; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800012fd  mov     r8d, 10000h; unsigned int
0x180001303  mov     word ptr [rsp+48h+Args], r15w; unsigned __int16
0x180001309  mov     rcx, rbx; struct _DPS_MESSAGE *
0x18000130c  call    ?DpspSendASyncMessage@@YAJPEAU_DPS_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@KPEAXG@Z; DpspSendASyncMessage(_DPS_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,ulong,void *,ushort)
0x180001311  mov     esi, eax
0x180001313  test    eax, eax
0x180001315  jns     short def_1800011FD; jumptable 00000001800011FD default case
0x180001317  movzx   eax, ax
0x18000131a  mov     r8d, 3B1h; int
0x180001320  mov     dword ptr [rsp+48h+Args], eax; Args
0x180001324  lea     r9, aErrorD; "Error = %d"
0x18000132b  lea     rdx, aDpspsendclient; "DpspSendClientFeedback"
0x180001332  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001339  call    WdipTraceError
0x18000133e  jmp     short def_1800011FD; jumptable 00000001800011FD default case
0x180001340  mov     esi, 8007007Ah
0x180001345  mov     r14, [rsp+48h+arg_0]; jumptable 00000001800011FD default case
0x18000134a  mov     r15, [rsp+48h+arg_8]
0x18000134f  call    cs:__imp_GetProcessHeap
0x180001355  mov     r8, rbx; lpMem
0x180001358  xor     edx, edx; dwFlags
0x18000135a  mov     rcx, rax; hHeap
0x18000135d  call    cs:__imp_HeapFree
0x180001363  mov     rbx, [rsp+48h+arg_10]
0x180001368  mov     eax, esi
0x18000136a  mov     rbp, [rsp+48h+arg_18]
0x18000136f  add     rsp, 30h
0x180001373  pop     r12
0x180001375  pop     rdi
0x180001376  pop     rsi
0x180001377  retn
```
