# IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::enumReason)

- ea: `0x180006fc0`
- end: `0x18000703d`
- name: `?TranslateEnumReasonToString@DYNAMIC_COMPRESSION_NOT_SUCCESS@IISCompressionEvents@@SAPEBGW4enumReason@12@@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006bb0`

## callees

- `0x180006fc0`

## string_xrefs

- `0x180007022`: `ALREADY_CONTENT_ENCODING`
- `0x180006fe2`: `COMPRESSION_DISABLED`
- `0x180006fea`: `NO_COMPRESSION_10`
- `0x180006ff2`: `NO_COMPRESSION_PROXY`
- `0x18000702a`: `NO_COMPRESSION_RANGE`

## pseudocode

```c
const wchar_t *__fastcall IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case 1:
      result = L"NO_ACCEPT_ENCODING";
      break;
    case 2:
      result = L"COMPRESSION_DISABLED";
      break;
    case 3:
      result = L"NO_COMPRESSION_10";
      break;
    case 4:
      result = L"NO_COMPRESSION_PROXY";
      break;
    case 5:
      result = L"NO_MATCHING_SCHEME";
      break;
    case 6:
      result = L"UNKNOWN_ERROR";
      break;
    case 7:
      result = L"HEADERS_SENT_TWICE";
      break;
    case 8:
      result = L"NO_HEADER_SENT";
      break;
    case 9:
      result = L"NOT_SUCCESS_STATUS";
      break;
    case 10:
      result = L"ALREADY_CONTENT_ENCODING";
      break;
    case 11:
      result = L"NO_COMPRESSION_RANGE";
      break;
    case 12:
      result = L"NO_MATCHING_CONTENT_TYPE";
      break;
    default:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180006fc0  dec     ecx; switch 12 cases
0x180006fc2  cmp     ecx, 0Bh
0x180006fc5  ja      short def_180006FD8; jumptable 0000000180006FD8 default case
0x180006fc7  lea     rdx, cs:180000000h
0x180006fce  mov     eax, ds:(jpt_180006FD8 - 180000000h)[rdx+rcx*4]
0x180006fd5  add     rax, rdx
0x180006fd8  jmp     rax; switch jump
0x180006fda  lea     rax, aNoAcceptEncodi; jumptable 0000000180006FD8 case 1
0x180006fe1  retn
0x180006fe2  lea     rax, aCompressionDis; jumptable 0000000180006FD8 case 2
0x180006fe9  retn
0x180006fea  lea     rax, aNoCompression1; jumptable 0000000180006FD8 case 3
0x180006ff1  retn
0x180006ff2  lea     rax, aNoCompressionP; jumptable 0000000180006FD8 case 4
0x180006ff9  retn
0x180006ffa  lea     rax, aNoMatchingSche; jumptable 0000000180006FD8 case 5
0x180007001  retn
0x180007002  lea     rax, aUnknownError; jumptable 0000000180006FD8 case 6
0x180007009  retn
0x18000700a  lea     rax, aHeadersSentTwi; jumptable 0000000180006FD8 case 7
0x180007011  retn
0x180007012  lea     rax, aNoHeaderSent; jumptable 0000000180006FD8 case 8
0x180007019  retn
0x18000701a  lea     rax, aNotSuccessStat; jumptable 0000000180006FD8 case 9
0x180007021  retn
0x180007022  lea     rax, aAlreadyContent; jumptable 0000000180006FD8 case 10
0x180007029  retn
0x18000702a  lea     rax, aNoCompressionR; jumptable 0000000180006FD8 case 11
0x180007031  retn
0x180007032  lea     rax, aNoMatchingCont; jumptable 0000000180006FD8 case 12
0x180007039  retn
0x18000703a  xor     eax, eax; jumptable 0000000180006FD8 default case
0x18000703c  retn
```
